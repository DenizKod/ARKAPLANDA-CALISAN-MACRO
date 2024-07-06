# BU MACRO NE İŞE YARIYOR?

<p>- Bu Macro sizin önceden seçtiğiniz bir oyunu yada uygulamanızı arka plana atsanız bile sadece oyuna yada uygulamaya etki edecek şekilde tuş komutları gönderir. böylelikle siz ön planda eşzamanlı olarak websitelerinde surf yapabilir yada işleriniz halledebilirsiniz.


# BAŞLAYALIM

- Not Defterini Macro olarak kullanmak için tıpkı winrar gibi basit bir eklenti kurmanız gerek
- Google git > AutoHotKey > AutoHotKey 2.0 İndir

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/1f59df65-1711-46ee-9839-70a60de5b7d0)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/a8120c26-6290-4c18-a8ba-77bc2fcefdab)

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/cec10703-9864-43d0-9b38-0ca4dc5a58af)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/7e3297c2-1b29-4903-bfad-13e746833512)

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/98d9c31d-f1cb-4979-b6d3-483bf589c94f)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/54f0b575-8eda-4441-9886-d201f6321d5f)

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/b18ab5a4-081c-48ce-8df6-ef5da03d94b4)

# AŞAĞIDA KODU NOT DEFTERİNE YAPIŞTIR VE KAYDET

```
#Persistent
#NoEnv
SetTitleMatchMode, 2

windowTitle := "Lunar Client 1.8.9 (v2.16.0-2426)"
loopActive := false
isPaused := false

; Windows mesajlarını kullanarak tıklama işlemleri
WM_LBUTTONDOWN := 0x0201
WM_LBUTTONUP := 0x0202
WM_RBUTTONDOWN := 0x0204
WM_RBUTTONUP := 0x0205
WM_KEYDOWN := 0x0100
WM_KEYUP := 0x0101

; Betiği yükleme fonksiyonu
LoadScript() {
    Reload
    SetTimer, RunMacro, Off
    loopActive := false
    isPaused := false
    MsgBox, Betik yeniden yüklendi.
}

F2::
loopActive := true
isPaused := false
SetTimer, RunMacro, 10
return

F3::
isPaused := true
SetTimer, RunMacro, Off
ControlSend,, {a up}{w up}{d up}, %windowTitle%
PostMessage, %WM_LBUTTONUP%, , , , %windowTitle% ; Sol tıklamayı bırak
return

F4:: ; Betiği yeniden yükle
LoadScript()
return

RunMacro:
if (loopActive && !isPaused) {
    ; Sol tıklamayı başlat
    PostMessage, %WM_LBUTTONDOWN%, , , , %windowTitle%
    Sleep, 5
    ControlSend,, {a down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {a up}, %windowTitle%
    Sleep, 5
    ControlSend,, {w down}, %windowTitle%
    Sleep, 450
    ControlSend,, {w up}, %windowTitle%
    Sleep, 5
    ControlSend,, {d down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {d up}, %windowTitle%
    Sleep, 5
    ControlSend,, {w down}, %windowTitle%
    Sleep, 450
    ControlSend,, {w up}, %windowTitle%
    ; Sol tıklamayı bırak
    PostMessage, %WM_LBUTTONUP%, , , , %windowTitle%
    Sleep, 1
}
if (loopActive && !isPaused) {
    SetTimer, RunMacro, 10
}
return
```
![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/1f59df65-1711-46ee-9839-70a60de5b7d0)

![image](https://github.com/DenizKod/Oyunlar-Arkaplandayken-Calisan-Macro/assets/168285638/66b66221-6da1-49a5-b7f5-e8ece4ae2a25)

![image](https://github.com/DenizKod/Oyunlarda-Arkaplanda-Calisan-Macro/assets/168285638/1f59df65-1711-46ee-9839-70a60de5b7d0)

SCRİPTİN AKTİF OLDUĞU ANLAMINA GELİR

![image](https://github.com/DenizKod/Oyunlar-Arkaplandayken-Calisan-Macro/assets/168285638/b31ac6b0-cd41-4c85-a920-d0132ed190a0)


# NASIL ÇALIŞIR?

<p>- F2 (MACROYU BAŞLATIR)
<p>- F3 (MACROYU DURDUR)
<p>- F4 (MACROYA RELOAD) F3 BASMADAN BUNA BASMAYIN ÇÜNKÜ MACRO DURMAZ

---------------------------------------------

# KENDİ TUŞ TAKIMLARINI NASIL OLUŞTURURSUN?

<p> Öncelikle aşağıdaki kod fark ettiyseniz "a tuşuna 26850 milisaniye bas" gibi kodlar içeriyor. Eğer kendi oyununuza özel bir tuş komutları oluşturmak istiyorsanız ama "ben bu işlerden hiç anlamam" diyorsanız; Yukarıdaki kodun tam halini CHATGPT'ye gönderin ve basmak istediğiniz tuşların milisaniyelerini ve sırasını yapay zekaya insana anlatır gibi anlatın. Ardından yapay zekaya kodun size düzeltmiş halini tam haliyle geri vermesini isteyin. 

(DİKKAT EDİN ! Yapay Zeka sadece tuş komutlarını bölümünü değiştirsin ve kodların ControlSend,, komutu içerdiğine dikkat edin. ÇÜNKÜ ! kodun içerisindeki ControlSend,, komutu sayesinde oyun arkaplandayken tuş komutları gönderebiliyorsunuz.)

```
RunMacro:
if (loopActive && !isPaused) {
    ; Sol tıklamayı başlat
    PostMessage, %WM_LBUTTONDOWN%, , , , %windowTitle%
    Sleep, 5
    ControlSend,, {a down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {a up}, %windowTitle%
    Sleep, 5
    ControlSend,, {w down}, %windowTitle%
    Sleep, 450
    ControlSend,, {w up}, %windowTitle%
    Sleep, 5
    ControlSend,, {d down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {d up}, %windowTitle%
    Sleep, 5
    ControlSend,, {w down}, %windowTitle%
    Sleep, 450
    ControlSend,, {w up}, %windowTitle%
    ; Sol tıklamayı bırak
    PostMessage, %WM_LBUTTONUP%, , , , %windowTitle%
    Sleep, 1
}
if (loopActive && !isPaused) {
    SetTimer, RunMacro, 10
}
return
```

### YUKARDAKİ KOD TAM OLARAK NE YAPIYOR?
<p>- mouse sol click basılı tut
<p>- a tuşuna basılı tut 26850 saniye
<p>- a tuşuna basmayı bırak
<p>- w tuşuna 450 milisaniye bas
<p>- w tuşuna basmayı bırak
<p>- d tuşuna basılı tut 26850 saniye
<p>- d tuşuna basmayı bırak
<p>- w tuşuna 450 milisaniye bas
<p>- w tuşuna basmayı bırak
<p>- mouse sol click basmayı bırak

---------------------------------------------

# KRİTİK TAVSİYELER (OKUMADAN SAYFAYI KAPATMA)

<p>- Controlsend,, ve PostMessage, kodları sayesinde oyunu önplana getirmeden hem klavye hem de mouse tuşlarına basabiliyoruz.
<p>- oynadığınız oyunu pencere moduna alın böylelikle oyunu 2. monitörde yada daha ufak bir pencere yaparsanız daha kolay takip edebilirsiniz.
<p>- Takıldığınız yada kodlara güncelleme yapmak için ChatGPT kullanın. çok güzel şeyler ekleyebilir kodunuza.

<p> Controlsend,, (Klavye tuşları için)
<p> PostMessage, (Mouse tuşları için)

#### (Mouse Sol click kodu)

<p> PostMessage, %WM_LBUTTONDOWN%, , , , %windowTitle%
    
#### (Mouse Sağ click kodu)
<p> PostMessage, %WM_RBUTTONDOWN%, , , , %windowTitle%

---------------------------------------------

# MİNECRAFT MACROSU YAPACAKLAR BURAYI KESİN OKUSUN

<p> Minecraft'da eğer oyun penceresi seçili değilse Pause ekranı açılır. bunun olmasını engellemek için aşağıdaki adımları uygula

1 - C:\Users\bilgisayar kullanıcı adını yaz\AppData\Roaming\.minecraft ve Minecraft klasörüne git

2 - Options'u txt olarak aç

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/77195dc9-0a7b-4da4-a875-c426e143f92e)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/aab94cb2-89ef-4ca5-9ca6-63576bd4cb66)

### ARTIK OYUN ARKA PLANA ATILDIĞINDA PAUSE OLMAYACAK

