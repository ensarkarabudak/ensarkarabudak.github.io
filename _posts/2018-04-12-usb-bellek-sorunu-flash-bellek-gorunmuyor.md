---
layout: post
title: "Usb Bellek Sorunu[Flash Bellek Görünmüyor]"
---

Linux dağıtımlarında veya ubuntu dağıtımında usb bellek görmüyor yani usb bellek sorunu ile karşılaşıyorsanız çözümü şu şekilde olacak.

Usb bellek sorunu çıktının şu şekilde ise:
**error mounting /dev/sdd1 at /media/hellofriend/8885-F4F7: Command-line `mount -t “exfat” -o“uhelper=udisks2,nodev,nosuid,uid=1000,gid=1000,iocharset=utf8,namecase=0,errors=remount-ro,umask=0077 “/dev/sdd1” “/media/hellofriend/8885-F4F7″‘ exited with non-zero exit status ..** şeklinde devam ediyorsa Exfat desteğini yüklemeniz gerekir bunun için aşağıdaki komutla exfat desteğini yükleyin.

```
sudo apt-get install exfat-fuse exfat-utils
```

## 

Usb belleğinizin sorununu gidermek için tekrar takıp çıkartın.Eğer görmezse aşağıdaki komutu çalıştırın.



```
sudo mount.exfat /dev/sdd1/*kullanıcı_adınız*/mount/point
```