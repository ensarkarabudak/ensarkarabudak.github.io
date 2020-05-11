---
layout: post
title: "SSID nedir? SSID Gizleme Nasıl Yapılır?"
---

#### SSID nedir?

**SSID(Service Set IDentifier)** evlerinizde,işyerlerinizde ya da farklı noktalarda 802.11 kablosuz yerel alan ağıyla(WLAN) ile ilişkilendiren birincil addır.Yani **Wi-Fi** ile seçim alanında seçeciğiniz kablosuz ağların bulunduğu her bir ağ bir SSID’dir.

Bir kablosuz ağın adını tanımlamak için SSID dediğimiz tanımlama ilecihazımızı daha rahat ve kolay biçimde seçip bağlanmamızı sağlar.

**32 karakterde**n oluşur.Büyük/küçük harf duyarlıdır.Son karakter sonlandırma karakteri olarak kullanılır genelde.İsiminizi güvenliğiniz için olabildiğince düşünülmüş bir isim koymanız uygun olacaktır.

#### SSID Nasıl Değiştirilir?

SSID isiminizi değiştirmek için router veya ADSL modemizine bağlanın.
Ardından **Wireless->Wireless Settings->Wireless Network Name** Kısmını değiştirip kaydederek değiştirebilirsiniz.

#### SSID Nasıl Gizlenir? – SSID Gizleme – Wifi Ağı Gizleme

SSID isiminizi gizlemek için router veya ADSL modemizine bağlanın.
Ardından Wireless->Wireless Settings->Enable SSID Broadcast yerini pasif olarak değiştirip kaydederek değiştirebilirsiniz.

#### Linux Üzerinde Ağ Konfigrasyonu – Linux SSID Ayarı Nasl Yapılır?

Öncelikle kablosuz cihazımızı bağlanalım.Genelde varsayılan ad wlan0’dır.Sizlerde farklı ise
burayı değiştirip bağlanın.

```
ifconfig wlan0 up
```

Daha sonra ağı tarayın.
`iwlist wlan0 scan`

Taramanın sonrasın aşağıdaki gib bir çıktı görmelisiniz:

```
ESSID: "NETWORK_NAME"
```

NETWORK_NAME kısmına ağınızın ismini girin.

Eğer SSID ve Şifresi bilen bir ağa bağlanmak istiyorsanız şu şekilde bağlanmalısınız:

```
iwconfig wlan0 essid Ağ_ismi key Ağ_Şifresi
```

Bağlantınızı yaptıktan sonra, aşağıdaki gibi dhclient komutunu kullanarak makineniz için bir IP adresi almalısınız:



```
dhclient wlan0
```