# ARKAPLANDA-CALISAN-MACRO

### ADIM 1 (YAPMANIZ 5 DAKİKA SÜRECEK)

- Not Defterini Macro olarak kullanmak için tıpkı winrar gibi basit bir eklenti kurmanız gerek
- Google git > AutoHotKey > AutoHotKey 2.0 İndir


![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/a8120c26-6290-4c18-a8ba-77bc2fcefdab)


![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/7e3297c2-1b29-4903-bfad-13e746833512)


![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/54f0b575-8eda-4441-9886-d201f6321d5f)


# AŞAĞIDA KODU NOT DEFTERİNE YAPIŞTIR VE KAYDET

```
#Persistent
#NoEnv
SetTitleMatchMode, 2

windowTitle := "OYUN PENCERESİNİN İSMİNİ PARANTEZİN İÇİNE YAZIN"
loopActive := false
isPaused := false

; Macro
LoadScript() {
    Reload
    SetTimer, RunMacro, Off
    loopActive := false
    isPaused := false
    MsgBox, Macro
}

F2::
loopActive := true
isPaused := false
SetTimer, RunMacro, 10
return

F3::
isPaused := true
SetTimer, RunMacro, Off
ControlSend,, {x up}{a up}{w up}{d up}, %windowTitle%
return

F4:: ; Macroyu tazele
LoadScript()
return

RunMacro:
if (loopActive && !isPaused) {
    ControlSend,, {x down}, %windowTitle%
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
    ControlSend,, {x up}, %windowTitle%
}
if (loopActive && !isPaused) {
    SetTimer, RunMacro, 10
}
return
```

### ADIM 2

<p>- F2 (MACROYU BAŞLATIR)
<p>- F3 (MACROYU DURDURUR)
<p>- F4 (MACROYA RELOAD) F3 BASMADAN BUNA BASMAYIN ÇÜNKÜ MACRO DURMAZ

## KENDİ MACRONU OLUŞTUR

```
RunMacro:
if (loopActive && !isPaused) {
    ControlSend,, {x down}, %windowTitle%
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
    ControlSend,, {x up}, %windowTitle%
}
if (loopActive && !isPaused) {
    SetTimer, RunMacro, 10
}
return
```

### YUKARDAKİ KOD TAM OLARAK NE YAPIYOR?
<p>- x tuşuna basılı tut
<p>- a tuşuna basılı tut 26850 saniye
<p>- a tuşuna basmayı bırak
<p>- w tuşuna 450 milisaniye bas
<p>- w tuşuna basmayı bırak
<p>- d tuşuna basılı tut 26850 saniye
<p>- d tuşuna basmayı bırak
<p>- w tuşuna 450 milisaniye bas
<p>- w tuşuna basmayı bırak
<p>- x tuşuna basmayı bırak

<p>- Fark ettiyseniz ControlSend,, {x up}, kodunu en alt kısma koyduğum için tüm bu tuşlara basma sırasında x tuşuna hep basılı tutarak yaptı


### MANTIĞI KAVRAMANIZ İÇİN EKSTRA ÖRNEK
```
  ControlSend,, {x down}, %windowTitle%
    Sleep, 5
    ControlSend,, {a down}, %windowTitle%
    Sleep, 26850
    ControlSend,, {a up}, %windowTitle%
    Sleep, 5
    ControlSend,, {x up}, %windowTitle%
    <p>- w tuşuna 450 milisaniye bas
    <p>- w tuşuna basmayı bırak
```

<p>- Eğer kod sıralamasını yukarıdaki gibi yapsaydım x tuşuna basmayı bırakmayı a tuşuna basmayı bitirdikten sonra bırakırdı ve w tuşuna geldiğinde artık x tuşuna basmadan diğer tuşlara basardı. umarım mantığını anlamışsınızdır.




# TAVSİYELER

<p>- oynadığınız oyunu pencere moduna alın, böylelikle oyunu 2. monitörde yada ufak bir pencerede takip edebilirsiniz.
<p>- Takıldığınız, yada kodlara güncelleme yapmak için ChatGPT kullanın, çok güzel şeyler ekleyebilir kodunuza.
<p>- ChatGPT'ye insana anlatır gibi anlatırsanız ne istediğiniz ve benim kodumu verirseniz size daha güncel ve oyununuza uygun bir şey verebilir.


### KRİTİK NOT, LÜTFEN OKU !
<p>- ControlSend özelliği sayesinde hedef pencereye arka plandayken bile macro yapabiliyoruz. ama bu sadece klavye tuşları için oluyor diye biliyorum. oyundaki mouse1, mouse2 tuşunuzu "X" benzeri bir tuşa taşıyın benim yaptığım gibi.


## MİNECRAFT MACROSU YAPACAKLAR BURAYI KESİN OKUSUN

1 - C:\Users\bilgisayar kullanıcı adını yaz\AppData\Roaming\.minecraft ve Minecraft klasörüne git

2 - Options'u txt olarak aç

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/77195dc9-0a7b-4da4-a875-c426e143f92e)

![image](https://github.com/DenizKod/ARKAPLANDA-CALISAN-MACRO/assets/168285638/aab94cb2-89ef-4ca5-9ca6-63576bd4cb66)

### ARTIK OYUN ARKA PLANA ATILDIĞINDA PAUSE OLMAYACAK

