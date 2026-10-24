"engine.dll"

"sub_1007D120" / "55 8B EC 81 EC ? ? ? ? A1 ? ? ? ? 33 C5 89 45 FC 56 E8 ? ? ? ? 8B F0 83 7E 68 02 0F 8C"

IDA pseudocode:


void __usercall sub_1007D120(char a1@<bl>, int a2@<edi>, float a3, char a4)
{
  int v4; // esi
  int v5; // edi
  int v6; // eax
  unsigned __int8 (__thiscall *v7)(int); // edx
  int v8; // edx
  int i; // ebx
  int v10; // edi
  char v11; // al
  double v12; // st7
  double v13; // st7
  double v14; // st7
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // edx
  int v20; // ecx
  int v21; // eax
  bool v22; // zf
  double v23; // st7
  float v24; // xmm0_4
  double v25; // st4
  double v26; // st5
  double v27; // st7
  double ArgList; // [esp+1Ch] [ebp-ACh]
  char v30; // [esp+24h] [ebp-A4h]
  void **v31; // [esp+2Ch] [ebp-9Ch] BYREF
  char v32; // [esp+30h] [ebp-98h]
  int v33; // [esp+34h] [ebp-94h]
  int v34; // [esp+3Ch] [ebp-8Ch]
  int v35; // [esp+40h] [ebp-88h]
  double v36; // [esp+44h] [ebp-84h]
  int v37; // [esp+4Ch] [ebp-7Ch]
  int v38; // [esp+50h] [ebp-78h]
  double v39; // [esp+54h] [ebp-74h]
  int v40; // [esp+5Ch] [ebp-6Ch]
  int v41; // [esp+60h] [ebp-68h]
  char v42; // [esp+64h] [ebp-64h]
  double v43; // [esp+6Ch] [ebp-5Ch]
  int v44; // [esp+74h] [ebp-54h]
  int v45; // [esp+78h] [ebp-50h]
  int v46; // [esp+80h] [ebp-48h]
  int v47; // [esp+84h] [ebp-44h]
  int v48; // [esp+88h] [ebp-40h]
  int v49; // [esp+8Ch] [ebp-3Ch]
  int v50; // [esp+90h] [ebp-38h]
  int v51; // [esp+94h] [ebp-34h]
  int v52; // [esp+9Ch] [ebp-2Ch] BYREF
  int v53; // [esp+A0h] [ebp-28h]
  float v54; // [esp+A4h] [ebp-24h]
  char v55; // [esp+ABh] [ebp-1Dh]
  int v56; // [esp+ACh] [ebp-1Ch] BYREF
  int v57; // [esp+B0h] [ebp-18h]
  int v58; // [esp+B4h] [ebp-14h] BYREF
  int v59; // [esp+B8h] [ebp-10h]
  int v60; // [esp+BCh] [ebp-Ch]
  char v61; // [esp+C0h] [ebp-8h]

  v4 = sub_10082CA0();
  if ( *(int *)(v4 + 104) >= 2 && (unsigned __int8)sub_1018C4C0() )
  {
    v30 = a1;
    v52 = 0;
    v53 = 0;
    if ( g_Telemetry )
      (*(void (**)(_DWORD, int *, _DWORD, int, _DWORD, _DWORD, const char *, int, void *, const char *, ...))(g_Telemetry + 80))(
        g_Telemetry,
        &v52,
        0,
        50,
        0,
        0,
        "cl_main.cpp",
        2585,
        &unk_104FD8B8,
        "%s",
        "CL_Move");
    v49 = v52;
    v5 = g_Telemetry;
    v6 = *(_DWORD *)dword_104EF2F0;
    v50 = v53;
    v7 = *(unsigned __int8 (__thiscall **)(int))(v6 + 24);
    v51 = g_Telemetry;
    v55 = 1;
    if ( !v7(dword_104EF2F0) )
    {
LABEL_8:
      if ( (!(*(unsigned __int8 (__thiscall **)(_DWORD))(**(_DWORD **)(v4 + 16) + 24))(*(_DWORD *)(v4 + 16))
         || *(_DWORD *)(dword_1069688C + 48))
        && (*(double *)(v4 + 112) > dbl_106B2B48
         || !(*(unsigned __int8 (__thiscall **)(_DWORD))(**(_DWORD **)(v4 + 16) + 228))(*(_DWORD *)(v4 + 16))
         || !a4) )
      {
        v55 = 0;
      }
      if ( *(_DWORD *)(v4 + 104) == 6 )
      {
        v8 = (int)*off_104268E4;
        LODWORD(v54) = *(_DWORD *)(v4 + 19012) + *(_DWORD *)(v4 + 19016) + 1;
        for ( i = (*(int (__thiscall **)(int (***)()))(v8 + 32))(off_104268E4);
              i != -1;
              i = ((int (__thiscall *)(int (***)()))(*off_104268E4)[9])(off_104268E4) )
        {
          sub_10052450("cl_main.cpp", 2626, i);
          if ( ((unsigned __int8 (__thiscall *)(int (***)(), int, int))(*off_104268E4)[13])(off_104268E4, i, a2) )
          {
            sub_100524A0(&v58);
          }
          else
          {
            v10 = *(_DWORD *)dword_104EE780;
            v11 = sub_10090580(v4);
            (*(void (__thiscall **)(int, float, _DWORD, bool))(v10 + 80))(
              dword_104EE780,
              COERCE_FLOAT(LODWORD(v54)),
              *(float *)&dword_1042FFBC - a3,
              v11 == 0);
            if ( (*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)dword_104EE8DC + 16))(dword_104EE8DC) )
              (*(void (__thiscall **)(int, float))(*(_DWORD *)dword_104EE8DC + 36))(
                dword_104EE8DC,
                COERCE_FLOAT(LODWORD(v54)));
            sub_100524A0(&v58);
            v5 = v51;
          }
          a2 = i;
        }
        if ( !v55 )
        {
          (*(void (__thiscall **)(_DWORD))(**(_DWORD **)(v4 + 16) + 184))(*(_DWORD *)(v4 + 16));
          ++*(_DWORD *)(v4 + 19016);
LABEL_55:
          if ( v5 )
            (*(void (__stdcall **)(int, int, int, _DWORD, _DWORD, _DWORD))(v5 + 84))(v5, v49, v50, 0, 0, 0);
          return;
        }
        sub_1007CEC0();
      }
      if ( v55 )
      {
        if ( (*(unsigned __int8 (__thiscall **)(_DWORD, int))(**(_DWORD **)(v4 + 16) + 28))(*(_DWORD *)(v4 + 16), a2)
          && !(*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)dword_104EF2F0 + 24))(dword_104EF2F0)
          && *(_DWORD *)(v4 + 104) == 6 )
        {
          v57 = 1065353216;
          v58 = 1065353216;
          v56 = 2;
          v61 = 0;
          v59 = 1045220557;
          v60 = 1045220557;
          sub_100A46C0((int)&v56, "WARNING:  Connection Problem", v30);
          v54 = ((double (__thiscall *)(_DWORD))*(_DWORD *)(**(_DWORD **)(v4 + 16) + 104))(*(_DWORD *)(v4 + 16));
          v12 = ((double (__thiscall *)(_DWORD))*(_DWORD *)(**(_DWORD **)(v4 + 16) + 88))(*(_DWORD *)(v4 + 16));
          if ( v54 - v12 <= 0.0 )
          {
            v54 = 0.0;
            v14 = 0.0;
          }
          else
          {
            v13 = ((double (__thiscall *)(_DWORD))*(_DWORD *)(**(_DWORD **)(v4 + 16) + 88))(*(_DWORD *)(v4 + 16));
            v14 = v54 - v13;
          }
          ArgList = v14;
          v56 = 3;
          sub_100A46C0((int)&v56, "Auto-disconnect in %.1f seconds", SLOBYTE(ArgList));
          v15 = sub_1021DC50();
          (*(void (__thiscall **)(int))(*(_DWORD *)v15 + 156))(v15);
          sub_10054240("connection problem");
        }
        v16 = sub_10192640();
        if ( byte_106970A2 || v16 == 2 || v16 == 4 )
        {
          if ( dword_106E0B14 )
          {
            v17 = (*(int (__thiscall **)(int))(*(_DWORD *)dword_106E0B14 + 36))(dword_106E0B14);
            if ( v17 )
            {
              if ( (*(int (__thiscall **)(int))(*(_DWORD *)v17 + 4))(v17) )
              {
                v18 = sub_10288620("System/lock", (int)Locale);
                if ( !sub_10284320(v18, "SteamServersDisconnected") )
                {
                  v57 = 1065353216;
                  v58 = 1065353216;
                  v59 = 1056964608;
                  v56 = 7;
                  v61 = 0;
                  v60 = 0;
                  sub_100A46C0((int)&v56, "WARNING:  Steam Servers Disconnected", v30);
                }
              }
            }
          }
        }
        if ( *(_DWORD *)(v4 + 104) == 6 )
        {
          v36 = 0.0;
          v19 = *(_DWORD *)(v4 + 204);
          v39 = 0.0;
          v20 = *(_DWORD *)(v4 + 16);
          v43 = 0.0;
          v47 = dword_10695E1C;
          v46 = v19;
          v34 = 0;
          v35 = 0;
          v37 = 0;
          v38 = 0;
          v40 = 0;
          v41 = 0;
          v42 = 0;
          v44 = 0;
          v45 = 0;
          v33 = 0;
          v31 = &NET_Tick::`vftable';
          v32 = 0;
          v48 = dword_10695E20;
          (*(void (__thiscall **)(int, void ***, _DWORD, _DWORD))(*(_DWORD *)v20 + 164))(v20, &v31, 0, 0);
        }
        v21 = (*(int (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)(v4 + 16) + 188))(*(_DWORD *)(v4 + 16), 0);
        v22 = *(_DWORD *)(v4 + 104) == 6;
        *(_DWORD *)(v4 + 19012) = v21;
        *(_DWORD *)(v4 + 19016) = 0;
        if ( v22 )
        {
          v23 = 1.0 / ((double (__thiscall *)(int *))*(_DWORD *)(*off_1042AA54[0] + 76))(off_1042AA54[0]);
          v54 = v23;
          if ( v23 <= *(float *)&dword_1042FFBC )
            v24 = v54;
          else
            v24 = *(float *)&dword_1042FFBC;
          v54 = v24;
          v25 = dbl_106B2B48 - *(double *)(v4 + 112);
          v26 = v24;
          if ( v25 > v24 || (v26 = v25, v25 >= 0.0) )
            v27 = dbl_106B2B48 + v23 - v26;
          else
            v27 = dbl_106B2B48 + v23 - 0.0;
        }
        else
        {
          v27 = dbl_106B2B48 + 0.2;
        }
        *(double *)(v4 + 112) = v27;
      }
      goto LABEL_55;
    }
    if ( *(_BYTE *)(v4 + 19036) )
    {
      v55 = 0;
      goto LABEL_8;
    }
    if ( g_Telemetry )
      (*(void (__stdcall **)(_DWORD, int, int, _DWORD, _DWORD, _DWORD))(g_Telemetry + 84))(
        g_Telemetry,
        v49,
        v50,
        0,
        0,
        0);
  }
}



<img width="1916" height="884" alt="image" src="https://github.com/user-attachments/assets/a3a0920f-7bdf-40a9-9a28-8612e2fcb754" />


o clmove bu işte speedhackin yani move modulationun ayrıca bfinaltick abuseunun aka eski rapidin ana fonksiyonu. 

<img width="541" height="33" alt="image" src="https://github.com/user-attachments/assets/acaafce0-bea9-4a4b-98d5-eae1530b79c7" />

a3 flAccumulatedExtraSamples oluyor
a4 bFinalTick bu onemli cunku bu mevcut karenin son işlem adımı mı olduguna bakan flag paketin gönderilmesi için kritik bir onay flagidir


<img width="479" height="55" alt="image" src="https://github.com/user-attachments/assets/fe79ec3b-226b-4528-8c70-ef8d0cdf4aa2" />
v4 basitce client state bu arada butun olay burada dönüyor kalan sacma netchan seyleri vesaire alakasız boş her seyi bastan anlatacagım zaten 
v4 = sub_10082CA0() getclientstate oluyor basitce // A1 ?? ?? ?? ?? 83 C0 08 bunu da kullanabilirsiniz 
ayrıca attıgım ssteki sub_1018C4C0() denen func Loopback diye gecer bot macında mısın versusta mı falan ona gore davranıs aldıran fonksiyon bu 




<img width="798" height="178" alt="image" src="https://github.com/user-attachments/assets/c9548d9f-1561-4961-a346-e88014843c8a" />
v55 flag bu oc zaten bir yerden tanıdık gelir bilenlere. Fakelag ana fonksiyonu bu flagdir canpacket denen sacmalıgın veya paketin gonderilip gonderilmeyecegini burası belirliyor 
v55 = 0 oldugu zaman choke atıyor basitce buraya kadar klasikti ve bilinen seyler. asıl olaya şimdiki sste gelecegiz 




<img width="513" height="59" alt="image" src="https://github.com/user-attachments/assets/c655f95d-992e-4553-ab9b-f79e28ee760d" />
v54 değişkenine geldi sıra bu imputa alakalı en onemli şeylerden biri işte olay burada baslıyor. burdaki 19012 ve 19016yı aklınızda tutun 
olay bunlarda dönuyor. 19012 kısaca LOS (Last Out Sequence) oluyor VE ASIL ONEMLI OLAN 19016 bu sey choked commands oluyor basitce 
kısa formulu ve calısma mantıgı bu şekilde Son Komut + Biriken Komut + 1 = Üretilecek Yeni Komut Numarası





<img width="543" height="50" alt="image" src="https://github.com/user-attachments/assets/01721471-b7f9-40b3-a292-ef6af26b5013" />
bu da v54un işleyicisi. komutu alıyo ve o kadar usercmd uretiyor zaten olay burada choke exploitleri bu kısımda araya giriyor ve 
choked commands degerine 80 90 gibi absurt değerler yazıyorlar sonrasında cl move loop ile servera gonderiyorlar kısaca tek yaptıkları
sey bu.




<img width="779" height="138" alt="image" src="https://github.com/user-attachments/assets/c2504fe6-2a0c-4431-83db-fcd2545b0c08" />
burda ise if v55 == 0 olayı var canpacket false olursa paket gonderme durursa SetChoked() çağrılır ve 19016 yani aka choked commands 
sayacı kendi kendine 1 artırılır. burayla alakalı bazı insanların dusunmediği birşeyler dusundum onu da anlatacagım az sonra 








<img width="827" height="213" alt="image" src="https://github.com/user-attachments/assets/2cc30f25-0433-4c09-bbf7-e7670c847df4" />
sub_1007CEC0 burda da paketi gonderme olayı var şimdi olay şu burda bir clamp var 15 bu sınır burda duruyor istersen 10k yaz bu 15te duruyor
min(19016+1, 15) diye bir formulden geciyor e bunu bypass edemez miyiz şu bu onu da anlatacagım net sekilde hayır ama bir yere kadar da evet.
karmasık biraz 






<img width="733" height="66" alt="image" src="https://github.com/user-attachments/assets/4d4070b2-57d6-4bf4-89fa-b03c41e74109" />
Paket başarıyla gönderildikten sonra motor 19012yi hemen günceller ve 19016yı sıfırlar  Şimdi can sıkan kısım burası ve asıl fps loss burda cıkıyor
biz 19016 ya 90 yazsak bile,motor paketi gönderdiği anda orayı 0 yapar Bu yüzden değerleri her framede tekrar yazmamız gerekir bu da cpuyu cidden yorar
o yuzden buraya ADAM AKILLI yazılabilecek maks deger gozumde 80 veya 90dır bazı insanlar dusunuyor 500 yazarım o zaman falan. hayır bu sadece fpsini
yok eder veya sadece oyununu cokertir denemedim ama biliyorum denemeyin ogrenmeyin bombos ve gereksiz.





































