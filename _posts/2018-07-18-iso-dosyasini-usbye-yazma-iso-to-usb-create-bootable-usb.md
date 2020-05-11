---
layout: post
title: "ISO Dosyasını USB’ye Yazma(ISO to USB,Create Bootable Usb)"
tags:
  - iso
---

ISO Dosyasını USB’ye Nasıl Yazılır?,Bootable Usb Nasıl Yapılır?

Eğer Windows ortamında bir **iso** dosyasını usb’ye yazmak istiyorsanız [Rufus](https://rufus.akeo.ie/) adlı programı indirerek kolayca kurum yapabilirsiniz.Bilgisayarınıza format atmak istiyorsanız aşağıdaki adımları izleyin.

### WINDOWS işletim sistemi için

![image-center]({{ '/images/UsbToIso/usb-to-iso-nasıl-format-atılır-bootable.png' | absolute_url }}){: .align-center}

Aşağıdaki adımları izleyin:

1-Aygıtınızı seçin.
2-**BIOS yada MRB için UEFI** Bölüm Düzeni seçin.
3-FAT32 dosya sistemini seçin.
4-Ayırma birimi boyutunu **4096 byte(varsayılan)** olarak seçin.
5-Yeni birim etiketi olarak kendinizce bir isim verin.
6-Biçimlendirme seçeneklerinde herhangi bir değişiklik yapmanıza gerek yok.
7-**BAŞLAT**

### LINUX işletim sistemi için

UNIX tabanlı Linux işletim sistemlerinde ise bu işlemi komut satırından aşağıdaki yolla yapabilirsiniz.

**1-** `sudo umount /dev/<**disk**>`

**2-** `sudo dd if= of=/dev/<**disk**> bs=4m && sync`

> Not: **<\**disk\**>** kısmına kendi usb yolunuzu yazın.(örneğin:**/dev/sdd1**)
> kısmına kendi img,iso gibi dosyalarınızı yazabilirsiniz.