---
layout: post
title: "Linux Komut Satırında Bul ve Değiştir"
tags:
  - linux
---

Linux işletim sisteminde bir dosya içerisindeki istediğimiz kelimeyi bul ve değiştir yani find and replace işleminin nasıl yapıldığını inceleyeceğiz.Bu işlemi komut satırından yapacağız.Öncelikle örnek dosyamızın adı:ornek.txt olsun.

ornek.txt dosyasının içerisindeki içerik şu şekilde:

> find and replace pasajlarının ensar birçok çeşitlemesi vardır.Linux Komut Satırında Bul ve Değiştir çoğunluğu ensar mizah katılarak veya linux sözcükler eklenerek değiştirilmişlerdir.Eğer bir ensar pasajı ensar kullanacaksanız,metin aralarına sed komutu sözcükler karabudak gizlenmediğinden emin olmanız gerekir.ensar

Bu dosya içindeki **‘ensar’** ismini ‘**karabudak’** olarak değiştirmek istersek aşağıdaki komutu kullanmamız gerek.

```
sed -i -e 's/ensar/karabudak/g' ornek.txt
```

Çıktısı:

> find and replace pasajlarının karabudak birçok çeşitlemesi vardır.Linux Komut Satırında Bul ve Değiştir çoğunluğu karabudak mizah katılarak veya linux sözcükler eklenerek değiştirilmişlerdir.Eğer bir karabudak pasajı karabudak kullanacaksanız,metin aralarına sed komutu sözcükler karabudak gizlenmediğinden emin olmanız gerekir.karabudak

#### Linux Sistemlerde Bul ve Değiştir(Find and Replace) Kullanımı

Yani genel bir formül vermek istersek şu şekilde olacak:

```
sed -i -e 's/***değiştireceğiniz_kelime\***/***yeni_kelime\***/g' ornek.txt
```

Ben örnekte .txt dosyası üzerinde yaptım fakat siz istediğiniz dosya üzerinde yapabilirsiniz.Örneğin *.odt,*.doc,*.docx,*,*.conf,*.cfg.. dosyalarının içeriğini sed komutu ile toplu bul ve
değiştir(find and replace) yapabilirsiniz.