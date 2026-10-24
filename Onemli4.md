Son kısım da bu anlattıklarımı birleştiren ve rapid firei tetikleyen şey. kısaca CL move loop oluyor speedHack mekanizmasıenginein CL_Move fonksiyonunu 
 bir frame içinde birden fazla kez (N kez) çağırarak çalışır GetExtraCalls() uzerinden işler cok basit mantık oncekinde choke atıyorduk bunda ise 
 hepsini gonderiyoruz bir anda 
 "int GetExtraCalls()
{
    int n = bEnabled ? nValue : 0;
    return n < 0 ? 0 : n;
}"
kısaca yaptıgı eğer SpeedHack açıksa, senin belirlediğin nValue kadar ekstra çağrı sayısı döndürür 1000e kadar yazıyoruz bunu fakat belirli bir kısım sonrası
sadece fps dusuruyor. nValue 100 ise 1 kez calısacagı framede 100kez fazladan calısıyor moveloop atıyor bunu daha cok anlatıp zaman kaybetmek istemiyorum 
zaten yıllardır bilinen bir şey bRewind  kullanılabilir onemlidir hatta 
cpp
inline bool bRewind = false; 

bu da standart yöntemde biz CL_Move'u bir döngü for veya while içinde çağırırız. bRewind ise çok daha agresif bir CPU hilesidir (Return Address Rewinding) 
enginein call CL_Move komutunun return addressini manipüle ederek, CPU'nun aynı CL_Move komutunu baştan çalıştırmasını sağlar. motorun kendi iç akışında hatasız 
temiz komutlar üretmesini sağlar. normalde motor CL_Move'u her çağırdığında, o anki klavye/fare durumunu okur. Eğer sen SpeedHack açıkken M1 basılı tutarsan, 
motor 10 ekstra çağrının hepsinde ateş etmeye çalışır. Bu da SpeedHack'in istemeden bir RapidFire'a dönüşmesine neden olur.
