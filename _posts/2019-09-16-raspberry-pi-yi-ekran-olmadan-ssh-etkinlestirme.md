---
layout: post
title: "Raspberry Pi'yi Ekran Olmadan SSH Etkinleştirme"
author: ensarkarabudak

---

Başıma gelen ve oldukça kullanışlı olan bir bilgiyi paylaşmak istiyorum.

Problem: Sd(Hafıza) kartınıza Raspbian Buster işletim sistemini boot ettiniz.Kartı Raspberry Pi üzerine taktınız ve çevrenizde bir monitör veya HDMI kablosu yok.SSH ile uzaktan bağlantı yapmak istiyorsunuz.Nasıl bağlanırdınız?

İşte bu olay başıma geldi oldukça kolay bir çözümü var

SD(Hafıza) kartını bilgisayara takın ve boot ve rootfs olmak üzere iki tane bağlı aygıt  gözükmesi gerekir.Bunlarda boot adlı aygıta girip içine bir ssh adında dosya oluşturmamız gerek.

```bash
cd /media/user/boot 
touch ssh
```

Not: Sizde SD kartın yolu değişiklik gösterir. "/media/user/boot " kısmına kendinize göre düzeltmelisiniz.

Ardından  `wpa_supplicant.conf` adında bir dosya daha oluşturup içine aşağıdaki komutları yapıştırın.

```bash
nano wpa_supplicant.conf
```
```bash
country=IE 
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev 
update_config=1 
network={ 
scan_ssid=1 
ssid="wifi-network-name" 
psk="wifi-network-password" 
key_mgmt=WPA-PSK 
}

```

Not: ssid ve psk değerlerini düzeltmeniz gerekmektedir.

Raspberry Pi'nin IP adresini nasıl bulacağız derseniz nmap ile bulabilirsiniz.

Nmap'i kurun.

Mac: `brew install nmap`
Linux (ubuntu): `sudo apt-get install nmap`

Aşağıdaki komutu yazarak tarama yapın ve ağınıza bağlı olan cihazların IP adreslerini görebilirsiniz.

`nmap 192.168.0.1/24`

Buradan Raspberry Pi'nin IP adresini bularak. SSH ile uzaktan bağlanabilirsiniz.