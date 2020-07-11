---
layout: post
title: "Nvidia ile Intel Tümleşik Ekran Kartı Sorunu ve Çözümü(Bumblebee Kurulumu)"
tags:
  - sorun
---

Intel-Nvidia Hibrit GPU Sorunu ve Çözümü,Nvidia ile Intel Tümleşik Ekran Kartları arasında geçiş yapmak için Bumblebee adlı programın kurulumunu gerçekleştireceğiz.

Günümüzdeki yeni nesil laptop veya masaüstü bilgisayarlarda artık Nvidia ekran kartıyla
birlikte,gelişen işlemci teknolojiyle beraber **Intel** firması artık entegre ekran kartı bulundurabiliyor.

Nvidia,bu sorunu **‘Nvidia Optimus’** dediği yazılım ile işlemcimizdeki entegre edilmiş ekran kartının zorladığıişlemlerde ‘Nvidia Optimus’ devreye girerek **Nvidia GPU**‘yu devreye sokup işlemlerimizi rahatlıkla yapabiliyoruz.
Bu sayede **uzun pil süresi ve ısınmayı** önleyebiliriz.

Sisteminizde ‘Nvidia Optimus’ yazılımının çalışıp çalışmadığı anlamak için aşağıdaki sorguyu çalıştırın.

```
lspci | egrep 'VGA|3D|Display'
```

Bu komuttan sonra aşağıdaki gibi bir çıktı alıyorsanız Optimus destekli ekran kartınız mevcut demektir.

```
00:02.0 VGA compatible controller: Intel Corporation 4th Gen Core Processor Integrated Graphics Controller (rev 06)01:00.0 3D controller: NVIDIA Corporation GK208M [GeForce 920M] (rev ff)
```

Bu sorunu açık kaynak kodlu bir yazılım olan **Bumblebee** ile GPU’lar arası geçiş yapabileceksiniz.

Aşağıdaki komutları kullanarak Bumblebee uygulamasını başarıyla kurabilirsiniz.
`sudo add-apt-repository ppa:bumblebee/testing -ysudo add-apt-repository ppa:graphics-drivers/ppa -ysudo apt-get updatesudo apt-get install bumblebee nvidia-384 nvidia-settings bumblebee-nvidia primus virtualgl linux-headers-$(uname -r) -y`

64 bitlik sistemler için **Primus için 32 bit uyumluluk** kütüphanesini de kurunuz.

```
sudo apt-get install primus-libs-ia32
```

Kurulumdan sonra düzeltmeler yapmamız gerek ilk olarak **bumblebee.conf** dosyasını açalım.

```
sudo xed /etc/bumblebee/bumblebee.conf
```

Açılan sayfada aşağıdaki satırları bulunuz.

```
# (See also the driver-specific sections below)Driver=`
`# Module name to load, defaults to Driver if empty or unsetKernelDriver=nvidia-current
# colon-separated path to the nvidia librariesLibraryPath=/usr/lib/nvidia-current:/usr/lib32/nvidia-current
# default Xorg modules pathXorgModulePath=/usr/lib/nvidia-current/xorg,/usr/lib/xorg/modules
```

ve aşağıdaki şekilde değiştirip kaydedin.

```
# (See also the driver-specific sections below)Driver=nvidia
# Module name to load, defaults to Driver if empty or unsetKernelDriver=nvidia-384
# colon-separated path to the nvidia librariesLibraryPath=/usr/lib/nvidia-384:/usr/lib32/nvidia-384
# default Xorg modules pathXorgModulePath=/usr/lib/nvidia-384/xorg,/usr/lib/xorg/modules
```

Bumblebee.conf dosyasını düenledikten sonra varsayılan **GL sağlayıcısını** düzeltelim.
`sudo update-alternatives --set i386-linux-gnu_gl_conf /usr/lib/i386-linux-gnu/mesa/ld.so.confsudo update-alternatives --set x86_64-linux-gnu_egl_conf /usr/lib/x86_64-linux-gnu/mesa-egl/ld.so.confsudo update-alternatives --set x86_64-linux-gnu_gl_conf /usr/lib/x86_64-linux-gnu/mesa/ld.so.conf`

Nvidia-384 sürücüsünün başlangıçta etkin olamaması için sürücüyü **karalisteye** alalım.

```
echo -e '# 384 karaliste\nblacklist nvidia-384\nblacklist nvidia-384-updates\nblacklist nvidia-experimental-384' | sudo tee -a /etc/modprobe.d/bumblebee.conf
```

**GRUB** dosyasını düzenlememiz gerekiyor.

```
sudo xed /etc/default/grub
```

Açılan sayfada aşağıdaki satırı bulunuz.

```
GRUB_CMDLINE_LINUX=""
```

Şu şekilde değiştirip kaydedin.
`GRUB_CMDLINE_LINUX="nogpumanager"`

Daha sonra grub ayarlarını güncelleyip bilgisayarı yeniden başlatın.

```
sudo update-grubsudo reboot
```

Sisteminizi yeniden başlattıktan sonra **bbswitch-dkms ve nvidia-384** paketlerinin yeniden yapılandırın ve yeniden başlatalım.

```
sudo dpkg-reconfigure bbswitch-dkmssudo dpkg-reconfigure nvidia-384sudo reboot
```

Aşağıdaki komutla Bumblebee kurulumumuz başarı olduğu anlamak için aşağıdaki komutu çalıştırın.

```
glxgears
```

Ardından **Nvidia GPU** kullanımıyla test edin.

```
optirun glxgears
```

Bu komuttan sonra dönen çarklar görüyorsanız Bumblebee başarıyla çalışıyor demektir.
Bundan sonra **optirun** şeklinde kullanabilirsiniz

Terminal üzerinde çalıştırmak zor tabiki bunun için grafik arayüz kullanarak kolay bir şekilde
kullanabilirsiniz.Aşağıdaki komutları sırasıyla çalıştırın.

```
sudo apt-get install python-appindicatorwget -c --no-check-certificate https://www.dropbox.com/s/c7mxeekoz66w4on/bumblebee-ui.tar.gztar -xzvf bumblebee-ui.tar.gzcd bumblebee-uichmod +x ./INSTALLsudo ./INSTALL
```



Kurulum **başarıyla tamamlandı** menüden arayıp çalıştırabilirsiniz.