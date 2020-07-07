---
layout: post
title: "Arch Linux Kurulumu 2020(How to Install Arch Linux )"
tags:
  - linux
---

Arch Linux kurulumunu başlamadan önce Arch Linux sitesiden güncel iso dosyasını [buradan](https://www.archlinux.org/download/) indirin.

Doğrudan indirme seçeneğini veya torrent dosyasını kullanarak indirebilirsiniz.

Arch Linux iso dosyasını indirmeden önce, sisteminizde boş disk alanı ve en az 1 GB RAM’in bulunduğundan emin olun.

İndirdiğiniz iso dosyasını usb’ye boot edip bilgisayara bağladıktan sonra aşağıdaki ekrandan bilgisayarınızın işlemci mimarisine göre kurulum yapmak istediğiniz seçeneği belirleyiniz.32 bit kurulum yapacak iseniz i686 seçeneğini seçin.64 bit kurulum yapacak iseniz x86_64 seçeneği ile devam edin. Benim bilgisayarım 64 bit yani x86_64 seçeneği ile devam edeceğim.

Klavye düzenini ve font ayarını yapın.

```
loadkeys trqsetfont lat5-12
```

Kurulum esnasında paketler kurulacağı için kablolu internetiniz olması sizin avantajınıza olacaktır.Wifi ile bağlandıysanız aşağıdaki komut ile wifi üzerinden bir ağa bağlanın ve sizden şifresini isteyecektir.

(optional)`iw dev` komutuyla kablosuz ethernet kartınızı kontrol edip ismini öğrenebilirsiniz.
`wifi-menu`

İnternet bağlantısını yaptıktan sonra kontrol için aşağıdaki komutu girin.

```
ping google.com
```

Eğer ping sonuçlarını görebiliyorsanız internet bağlantınız başarıyla bağlanmıştır.

`cfdisk` komutuyla disk bölümleme kısmına geçiyoruz.

> Not:Sabit sürücünüzü bölümlendirmeniz için bir çok araç vardır.Eğer GPT bölümlendirme tablosu kullanıyorsanız **cgdisk** kullanmanız gerekiyor. Eğer MBR bölümlendirme tablosu ile yapacaksanız da **cfdisk** kullanacaksınız.

Disk yapısını UEFI kurulum için gpt,klasik BIOS sistemler için dos seçeneği ile devam edin.

Bu kısımda 3 adet disk bölümü oluşturmanız gerekmektedir.

Root bölümü.
GPT için BIOS boot bölümü.
Swap Bölümü.

Root Bölümü için
`New -> EnterFirst Sector -> EnterSize in Sector -> 40GB -> Enter (istediğiniz gibi boyutu değiştirebilirsiniz.)Hex Code of GUID (L to show pres, Enter = 8300) -> EnterEnter partition name – > Enter`

GPT için BIOS boot bölümü için
`New -> EnterFirst Sector -> EnterSize in Sector -> 1007KiB -> EnterHex Code of GUID (L to show pres, Enter = 8300) -> ef02 ->EnterEnter partition name – > Enter`

##### 

Swap bölümü için
Hit New -> Enter
First Sector -> Enter
Size in Sector -> 2GB -> Enter
Hex Code of GUID (L to show pres, Enter = 8300) -> Enter
Enter partition name – > swap

Bütün işlemleri yaptıktan sonra **‘write’** seçeneğini seçin.Yes yazıp ve devam edin.
Bölümlendirme işlemi aşağıdaki gibi olmalıdır.


Aşağıdaki komutları sırasıyla çalıştırın.
mkfs.ext4 /dev/sdaX(root bölümü için)
mkswap /dev/sdaY(swap bölümü için)
swapon /dev/sdaY(swap bölümü için)
mount /dev/sdaX /mnt

nano /etc/pacman.d/mirrorlist
pacstrap -i /mnt base base-devel

Paketlerin kurulumu için onay isteyecektir YES diyip ENTER’a basın.

genfstab -U -p /mnt >> /mnt/etc/fstab
arch-chroot /mnt
nano /etc/locale.gen(Dil ve bölge ayarı)
ln -s /usr/share/zoneinfo/[KITA]/[BÖLGE] > /etc/localtime(Zaman Ayarı)
hwclock –systohc –utc(Donanım Zaman Ayarı)
echo BİLGİSAYAR_ADI > /etc/hostname(Bilgisayarınızın adını belirleyin)

Depo ayarı
`nano /etc/pacman.conf`

```
[multilib]Innclude = /etc/pacman.d/mirrorlist // Yorum satırını kaldırın.
```

pacman -Sy

passwd(Root kullanıcının şifresini belirleyin)
useradd -m -g users -G wheel,storage,power -s /bin/bash KULLANICI_ADI(yeni kullanıcı oluşturun)
passwd KULLANICI_ADI(Kullanıcıya şifre belirleyin)
pacman -S sudo



EDITOR=nano visudo yazıp aşağıdaki yorum satırı kaldırın.
%wheel ALL=(ALL) ALL

pacman -S bash-completion

pacman -S grub
grub-install –target=i386-pc –recheck /dev/sda

pacman -S os-prober
grub-mkconfig -o /boot/grub/grub.cfg