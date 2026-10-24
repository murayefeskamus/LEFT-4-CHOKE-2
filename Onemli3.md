bu kısımda ise 15 sınırını anlatacagım bu aşılmaz cunku protokol bu yapılamayacak seyler hala var yani :D
herneyse baslangıcta baya aramıstım 4k bytelık buffer buldum "char v41[4000]" sanırım writeusercmd olayı tamamen onu gosterecegim
sonrasında neden işe yaramadıgını vesaire 


<img width="1911" height="829" alt="image" src="https://github.com/user-attachments/assets/8ccc4bb6-fdb8-44e9-b76e-8f938842f5d8" />


bu sub_1007CEC0 kısaca paket builder bu. benim de basta kandıgım olay buydu pseudocode tam olarak bu 


int __usercall sub_1007CEC0@<eax>(int a1@<edi>)
{
  _DWORD *v1; // esi
  int v2; // eax
  int v3; // edx
  int result; // eax
  int v5; // esi
  int v6; // ecx
  int v7; // esi
  int v8; // ecx
  int v9; // esi
  int v10; // edi
  bool v11; // al
  int v12; // eax
  void **v14; // [esp+4h] [ebp-1064h] BYREF
  char v15; // [esp+8h] [ebp-1060h]
  int v16; // [esp+Ch] [ebp-105Ch]
  int v17; // [esp+14h] [ebp-1054h]
  int v18; // [esp+18h] [ebp-1050h]
  double v19; // [esp+1Ch] [ebp-104Ch]
  int v20; // [esp+24h] [ebp-1044h]
  int v21; // [esp+28h] [ebp-1040h]
  double v22; // [esp+2Ch] [ebp-103Ch]
  int v23; // [esp+34h] [ebp-1034h]
  int v24; // [esp+38h] [ebp-1030h]
  char v25; // [esp+3Ch] [ebp-102Ch]
  double v26; // [esp+44h] [ebp-1024h]
  int v27; // [esp+4Ch] [ebp-101Ch]
  int v28; // [esp+50h] [ebp-1018h]
  int v29; // [esp+58h] [ebp-1010h]
  int v30; // [esp+5Ch] [ebp-100Ch]
  int v31; // [esp+64h] [ebp-1004h]
  char v32; // [esp+68h] [ebp-1000h]
  int v33; // [esp+6Ch] [ebp-FFCh]
  int v34; // [esp+70h] [ebp-FF8h]
  _BYTE v35[28]; // [esp+88h] [ebp-FE0h] BYREF
  _BYTE v36[16]; // [esp+A4h] [ebp-FC4h] BYREF
  int v37; // [esp+B4h] [ebp-FB4h]
  int v38; // [esp+B8h] [ebp-FB0h]
  int v39; // [esp+BCh] [ebp-FACh]
  int v40; // [esp+C0h] [ebp-FA8h]
  char v41[4000]; // [esp+C4h] [ebp-FA4h] BYREF

  v1 = (_DWORD *)(sub_10082CA0() + 19016);
  v39 = *(_DWORD *)(sub_10082CA0() + 19012) + *v1 + 1;
  v2 = sub_10082CA0();
  v3 = (int)*off_104268E4;
  v37 = *(_DWORD *)(v2 + 19016);
  result = (*(int (__thiscall **)(int (***)()))(v3 + 32))(off_104268E4);
  v5 = result;
  v40 = result;
  if ( result != -1 )
  {
    while ( 1 )
    {
      sub_10052450("cl_main.cpp", 2535, v5);
      if ( ((unsigned __int8 (__thiscall *)(int (***)(), int, int))(*off_104268E4)[13])(off_104268E4, v5, a1) )
      {
        sub_100524A0(v36);
      }
      else
      {
        v19 = 0.0;
        v17 = 0;
        v22 = 0.0;
        v18 = 0;
        v26 = 0.0;
        v20 = 0;
        v21 = 0;
        v23 = 0;
        v24 = 0;
        v25 = 0;
        v27 = 0;
        v28 = 0;
        v15 = 1;
        v16 = 0;
        v14 = &CLC_Move::`vftable';
        v32 = 0;
        v31 = 0;
        v33 = -1;
        v34 = 0;
        sub_1028F430(v35);
        v15 = 0;
        sub_1028F450(v41, 4000, 0, -1);
        v29 = 2;
        if ( v37 + 1 <= 15 )
          v6 = v37 + 1 < 0 ? 0 : v37 + 1;
        else
          v6 = 15;
        v7 = v39 - v6;
        v30 = v6;
        v8 = v39;
        v9 = v7 - 1;
        v10 = -1;
        v11 = 1;
        if ( v9 > v39 )
          goto LABEL_16;
        do
        {
          LOBYTE(v38) = v9 >= v8 - v30 + 1;
          v11 = v11
             && (*(unsigned __int8 (__thiscall **)(int, int, _BYTE *, int, int, int))(*(_DWORD *)dword_104EE780 + 88))(
                  dword_104EE780,
                  v40,
                  v35,
                  v10,
                  v9,
                  v38);
          v8 = v39;
          v10 = v9++;
        }
        while ( v9 <= v39 );
        if ( v11 )
        {
LABEL_16:
          v12 = sub_10082C70(-1);
          (*(void (__thiscall **)(_DWORD, void ***, _DWORD, _DWORD))(**(_DWORD **)(v12 + 16) + 164))(
            *(_DWORD *)(v12 + 16),
            &v14,
            0,
            0);
        }
        v14 = &INetMessage::`vftable';
        sub_100524A0(v36);
        v5 = v40;
      }
      a1 = v5;
      result = ((int (__thiscall *)(int (***)()))(*off_104268E4)[9])(off_104268E4);
      v40 = result;
      if ( result == -1 )
        break;
      v5 = v40;
    }
  }
  return result;
}





peki şimdi bu bize ne anlatıyor.   char v41[4000]; // [esp+C4h] [ebp-FA4h] BYREF acıkca gozukuyor 4k bytelık alan ayırıyor bende dusundum hani buraya 255 yazmayı basitce. 
<img width="361" height="28" alt="image" src="https://github.com/user-attachments/assets/aca53229-b699-46a7-ae2f-7e1eb403f882" />

ama şöyle bir sorun var burayı patchlemek pek bir işe yaramaz cunku buraya gelmeden bir kontrol var 

v37 = *(_DWORD *)(v2 + 19016);
// ...
if ( v37 + 1 <= 15 )
    v6 = v37 + 1 < 0 ? 0 : v37 + 1;
else
    v6 = 15; // o 15 command olayı burada işte 


engine 19016 sayacını okuyor. eğer sen oraya 45 yazdıysan, 45 + 1 = 46 olur. Ama 46 <= 15 olmadığı için else bloğuna düşer ve v6 = 15 yapar. Yani engine, senin 45 yazdığını görür
ama pakete sadece 15 tane koyar. kısaca bu hani buraya abartı değer yazarak fpsi zortlatmaya gerek yok benim gozumde. kısaca 15 protokolu kalkmaz cmp eax, 0Fh byte patch attık ve 
255 yazdık atıyorum gidip else v6 = 15; kısmındaki 15 değerini 255 yaptın. Motor artık v6 = 255 yapacak ve döngü 255 kere dönecek Bu fonksiyonun sonunda motor, paketi ağa yollamak için CLC_Move 
paketlerini serileştirir.İşte tam burada numnewcommands (yeni komut sayısı) alanı devreye girer. Bu alan 4 bittir. engine 255 yazmaya çalışır. Ağ paketi sadece son 4 biti okur.
Sunucu paketi aldığında yine 15 komut görür. kısaca hicbişey olmaz protokol bu. 

şimdi bu kısımda da olaya SendMoveOverride giriyor baya op bir şey. suanda net sekilde 15 komut sınırının motorun keyfi bir kararı değil, source engine ağ protokolünün
(4 bitlik numnewcommands alanı) fiziksel bir sınırı olduğunu ve bu sınırın istemci tarafında asla aşılamayacağını kanıtladık. Burada ise daha iyisi geliyor. onceden acıklayayım
sendmoveoverride denen şey bu 15 sınırını kaldırmıyor kaldıramaz cunku. bunun yaptıgı sey kısaca sub_1007CEC0a kucuk bir hook atıyor ve direkt kapatıyor. paketi tamamen kendi
yonetiyor. Ben buna kısaca SendMoveReplacer diyorum yada insanlar SendMoveOverride diyor. Normal şartlarda CL_Move fonksiyonu, paketi hazırlamak için sub_1007CEC0'ı çağırır.
Ancak engine bu fonksiyonu çağırmadan önce bir sürü Early-Out kapısından geçer mesela Bağlantı durumu tam 6 mı?CanPacket() true mu döndü, yani ağ zamanı geldi mi? 
bFinalTick (a4) parametresi doğru mu? gibi sacma sapan. ve eğer bu kapılardan biri başarısız olursa motor SendMove gonderme kararı alır (v55 = 0) ve paket yazıcıya hiç girmez.
komutlar içeride birikmeye devam eder biz SpeedHack veya RapidFire ile saniyede yüzlerce komut üretsek bile, motorun bu katı kuralları yüzünden o komutların çoğu paketlenmeden çöpe gider. bu da
bir hayli can sıkıyor. biz ne yapıyoruz: 
engine gibi karmaşık GetClientState çağrılarıyla uğraşmayız. Direkt raw adreslere gideriz:

cpp
auto pClientState = *reinterpret_cast<uintptr_t *>(hEngine + 4352236); 
auto pNetChannel = *reinterpret_cast<void **>(pClientState + 24);
// Birikmiş komutları ve son gönderilen komut numarasını oku 
const int nChoked = *reinterpret_cast<int *>(pClientState + 19024);
const int nLastOutgoing = *reinterpret_cast<int *>(pClientState + 19020);

Biz şuan motorun bekle kurallarını yıktık ama protokolün fiziksel kuralını yani o 4 bit olayını yıkamayız. Bu yüzden BuildAndSend() fonksiyonu, sınırı yine 15 olarak uygular:

cpp
// nChoked (19024) değeri ne olursa olsun, 15'i geçemez!
int nNewCommands = nChoked + 1;
if (nNewCommands > nMaxNew) // nMaxNew = 15
    nNewCommands = nMaxNew; 

bu da "Neden hala 15 sınırına takılıyoruz?" sorusunun cevabıdır. çünkü protokol 16. komutu okumaz


 Sunucuyu Kandırma Payı (nextCmd Bias):
İşte Choke değerinin (45, 80 vb.) asıl işe yaradığı yer burasıdır
cpp
// enginein lastcmdsi üzerine, chokedcmds ve +2 bias'ı ekle
const int nNextCommand = nLastOutgoing + nChoked + nNextCommandBias; 

// Bias = 2 Eğer nChoked (19024) değeri 45 ise, sıradaki komut numarası +47 ileri atlar. Paket yine 15 komut içerir ama sunucuya
"ben 47. komutu gönderiyorum" der. Sunucu bu boşluğu görünce Lag Compensation açmak zorunda kalır. bu yuzden sunucu tickrate duser



biz kendi clc movemuzu yapıyoruz
enginein kendi yapısını taklit ederek bir mesaj oluştururuz
cpp
CLC_Move_Message Message;
unsigned char Data[4000]; /
Message.Init(..., Data, sizeof(Data));
Message.SetNumNew(nNewCommands); 


Komutları Pakete Yazmak: (Vtable Çağrısı)
enginein kendi "komut yazıcı" fonksiyonunu (Vtable'dan) bulup, komutları tek tek pakete yazarız:

cpp
// Vtable + 88 (Slot 22) = WriteUsercmdDeltaToBuffer
auto pWriteUsercmd = (*reinterpret_cast<WriteUsercmd_t **>(pWriteUsercmdGlobal))[22];

int nTo = nNextCommand - nNewCommands;
int nFrom = -1;
while (nTo != nNextCommand)
{
    pWriteUsercmd(pWriteUsercmdGlobal, 0, Message.WriteTarget(), nFrom, nTo, true);
    nFrom = nTo;
    ++nTo;
} 


Ppaketi Zorla Yolla (SendNetMsg)
Normalde motorun bir sürü kontrolünden geçmesi gereken paket, bizim elimizde olduğu için direkt ağa fırlatılır

cpp
// Vtable + 164 (Slot 41) = SendNetMsg
auto pSendNetMsg = (*reinterpret_cast<SendNetMsg_t **>(pNetChannel))[41];

// Paketi yolla
pSendNetMsg(pNetChannel, &Message, nullptr, nullptr);




Kısaca bu şey tamamen bir sendmove replacerdir kuralları tanımaz kuralları kendi yazar.  



    



















