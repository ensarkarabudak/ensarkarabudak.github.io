---
layout: post
title: "Netbeans JDK ve Modül Etkinleştirilmedi Sorunu"
---

NetBeans programını açtığınızda veya yeni bir proje oluşturup “next” dediğinizde
Activation failed: Not all requested modules can be enabled gibibir hata ile karşılaştıysanız
Netbeans JDK’yı görmüyordur.Benzer şekilde şu şekilde bir çıktı hatası oluşacaktır:

![image-center]({{ '/images/Netbeans/NetBeans_JDK_hatası.jpg' | absolute_url }}){: .align-center}

Sorunun çözümü ise şu şekilde:

### 1.

“Netbeans.conf” adlı dosyayı bulup açın.Bu dosyayı windows kullananlar Disk C’ye girip aratarak kolayca bulabilirler.Linux kullananlar ise şu komut ile hangi adreste olduğunu bulup açsınlar
`find / -name netbeans.conf 2>/dev/null`

### 2.

Alt taraflarda JDK ile ilgili yerin olduğu yeri göreceksiniz.Şu şekilde

```
# Default location of JDK:# (set by installer or commented out if launcher should decide)## It can be overridden on command line by using --jdkhome
# Be careful when changing jdkhome.
# There are two NetBeans launchers for Windows (32-bit and 64-bit) and
# installer points to one of those in the NetBeans application shortcut
# based on the Java version selected at installation time.
#
#netbeans_jdkhome="/usr"
# Additional module clusters:# using ${path.separator} (';' on Windows or ':' on Unix):##netbeans_extraclusters="/absolute/path/to/cluster1:/absolute/path/to/cluster2"
```

### 3.

Burdaki **#netbeans_jdkhome=”/usr”** yolunu değiştirmemiz gerek
gene linux kullanıcıları **netbeans_jdkhome=”/usr/lib/jvm/java-8-openjdk-amd64″**
şu şekilde değiştirip kaydettiği taktirde çalışacaktır.Windows kullanıcıları ise
**netbeans_jdkhome=”C:\Program Files\Java\jdk1.8.0_67**” yapmalıdır.

### 4.

**.netbeans.conf** dosyasını kaydedin ve programı çalıştırın

> NOT: netbeans_jdkhome dosya yolu güncel jdk sürümüne göre değişicektir path üzerinde güncel dosya yolunu ve sürümü değiştirmeyi unutmayın.