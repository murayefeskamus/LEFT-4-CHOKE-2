Şimdi insanların yaptıgı seyi anlatacagım kısaca elimizde bazı exploitler Var Choke exploit en onemlisi ve bilineni bunun yaptıgı tek sey 
19016yı absurt derece şişirmek ve bunu fps loss olmadan yapmaktır buraya istersen 900 yaz tek olacak olan oyununun cokmesi yada 1fps falan
olması olacaktır. 80 90 yeterlidir. Kısaca olay client_state + 19024 yada v4 + 19016 degerine dogrudan manuel 90 yazmaktır.
Zaten basitce engine protokolu 15tir bunun ustune cıkamazsın yada azıcık cıkabilirsin onu da anlatacagım. 


Benim buldugum ekstra iyileştirmeler:

19036: bu no send flag yani oyunun kendi choke kombinasyonu otomatik 1 yazılıyor aslında ben bunu dusundum ve 15+1 yapabilecegimi fark ettim 
aslında baslandıcta dusuncem tamamen farklıydı oluru yok diye dusundum cunku bu dogrudan benim kendi choked commandsımı ezer ustune 0 yazar 
diye dusundum ama sonrasında hassas bir hook ile bunu lehime cevirebilecegime karar verdim. Ben bunun adını FORCECHOKE koymustum cunku
oyunun kendi choke mekanizmasını zorluyorum. Kısaca 19036'yı 1 yaparız. Motor komutları biriktirir. 5 frame sonra 19036'yı 0 yaparız.
Motor biriken komutları fırlatır mantıgı ile dusundum cunku bu direkt farklı bir gate yani çakısma imkanı yok




client_state + 112: bu da Next Cmd Time kısaca. Gerçek CALL_ORIGINAL yani framein kendi paketi çağrılmadan önce burayı 0 yaparsak, gerçek paket
de "yeni sample" üretir böylece sadece ekstra çağrılardan değil, ana frame'den de ekstra komut elde ederiz. Uygulanabilir ve denenmesinde sorun
olmayan bir şey bence




19012: Bu gozumde en hassas olanı ve olabilitesi dusuk denemedim sadece statik analiz sonucu yazıyorum. m_nLastOutgoingCommand bu seyin kısaca 
adı. CL_Move'un sonunda CALL_ORIGINAL sonrası bu değere +10 veya +20 eklersen, motor bir sonraki frame'de nextCmd'yi ve dolayısıyla v54'ü daha ileri atar.
Ben bunun olabilecegini dusundum. Chokeları stacklemek ve farklı gateler uzerinden sunucuya ben command choke atıyorum demenin farklı yolları bunlar 
(*(v4 + 19012) = v21;) bu da sorun olan sey. engine her paket gönderiminden sonra bu alanı kendi ağ sequence numarasıyla ezer kısaca her pakette 
bunu duzetlecek hassas bir hook gerekir 






Şimdi kısa kısa kod parcaları ile anlatacagım ne demek istediğimi. 


choke ve choke2 stacklenen:  (veya kafanızı kullanıp 2 nValue kullanmak yerine tek bir choke exploiti yazar ve buna tek value 90 verebilirsiniz.)
""{
    bool bChoke1 = Features::Exploits::ChokeExploit::IsActive();
    bool bChoke2 = Features::Exploits::ChokeExploit2::IsActive();

    if (bChoke1 || bChoke2)
    {
        // İkisi de açıksa değerleri TOPLA (+), sonra 19016 adresine yaz.
        s_nBleedChokeWriteValue = (bChoke1 ? Features::Exploits::ChokeExploit::nValue : 0)
                                + (bChoke2 ? Features::Exploits::ChokeExploit2::nValue : 0);
                                
        *reinterpret_cast<int *>(v4Bleed + 19016) = s_nBleedChokeWriteValue;
    }
}""


bleed:
""if (Features::Exploits::BleedExploitImproved::IsActive())
{
    // Yine aynı adrese kendi değerini ata (=)
    s_nBleedChokeWriteValue = Features::Exploits::BleedExploitImproved::nValue;
    *reinterpret_cast<int *>(v4Bleed + 19016) = s_nBleedChokeWriteValue; 
}""

permachoke: bu olayı cok uzun sure gizli tuttum. bu degeri kalıcı olarak yazıyor tusu bıraksanız bile tekrar 
bastıgınız anda choke degeri sıfırlanmıyor ustune yazılıyor

""local function permachoke()
    local client_state_ptr = read_int(engine + 4352236)
    if not client_state_ptr or client_state_ptr == 0 then return end

    local netchan = read_int(client_state_ptr + 24)
    if not netchan or netchan == 0 then return end

    write_int_safe(netchan + 16, -1)
    write_int_safe(netchan + 28, 255)
end""

forcechoke: 

""// CALL_ORIGINAL'den hemen önce çalışmalı!!!
if (Features::Exploits::ForceChoke::IsActive())
{
    *reinterpret_cast<unsigned char *>(v4Bleed + 19036) = 1; 
}
else
{
    // flagi sıfırla
    *reinterpret_cast<unsigned char *>(v4Bleed + 19036) = 0; 
}""


Seqchoke: Aşırı hassas bu kısımlar en ufak hatada crash. 
""// CALL_ORIGINAL'den hemen SONRA çalışmalı (Motor 19012'yi güncelledikten sonra)
if (Features::Exploits::Seqchoke::IsActive())
{
    int* pLastOutSeq = reinterpret_cast<int *>(v4Bleed + 19012);
    
    // Son gönderilen komut numarasına ekstra değer ekle (Örn: +10)
    *pLastOutSeq += Features::Exploits::Seqchoke::nValue; 
}""

RealFrameSampler:
""// Gerçek CALL_ORIGINAL'den hemen önce çalışmalı
if (Features::Exploits::RealFrameSampler::IsActive())
{
    // 112deki double değeri sıfırla
    *reinterpret_cast<double *>(v4Bleed + 112) = 0.0; 
}""













