---
layout: post
title: "Linear Search(Doğrusal Arama)"
tags:
  - algoritma
  - bilgisayar bilimleri
---

Linear Search (Doğrusal Arama)

En basit ve akla gelen ilk arama algoritmalarından biridir.Aynı **veri türüne sahip** elemanların arasında,istenilen elemanın olup olmadığını kontrol eder.

##### Linear Search Çalışma Mantığı

Veri türleri aynı olan bir veri kümesinde aranan elemanı,veri kümesinin ilk elemanından başlayarak teker teker kontrol ederek aramaktır.

Doğrusal aramanın(linear search**) zaman karmaşıklığı(time complexity) O(n)’dir.Bunun sebebi aradığımız veri,veri kümesinde yoksa ve n adet veri varsa bu bize algoritmanın zaman karmaşıklığının **O(n)** olduğunu belirtir.En iyi durumu,1’dir.Ortalama durumu,(n+1)/2 dir.

Bir örnek üzerinde inceleyelim.

Örnek:
Tam sayılardan oluşan bir dizi olsun.

4 – 18 – 25 – 1 – 9 – 89

şeklinde ve aradığımız tam sayı 9 olsun.

4 sayısından başlayarak teker teker kontrol ederek 5.adımda 9 sayısını bulur algoritmayı sonlandırır.

#### Linear Search (Doğrusal Arama) Örnekleri

![image-center]({{ '/images/DogrusalArama/linear_search-doğrusal-arama.gif' | absolute_url }}){: .align-center}

![image-center]({{ '/images/DogrusalArama/doğrusal-arama-nasıl-çalışır.gif' | absolute_url }}){: .align-center}

##### Linear Search Java Code(Doğrusal Arama Java Kodu)