---
layout: post
title: "Selection Sort (Seçerek Sıralama)"
tags:
  - algoritma
  - bilgisayar bilimleri
---

Selection Sort(Seçerek Sıralama) bir sıralama algoritmasıdır.Büyük veri kümesini sıralamak için verimsizdir.**Bubble sort** yönteminin iyileştirilmiş hali diyebiliriz.
Çünkü **takas işlemini** yapmaz.O notasyonu **O(n^2)**‘dir.
Bubble sort’a göre daha etkilidir.

#### Selection Sort(Selection Sort) Nasıl Çalışır?

Dizinin ilk elemanı geçici en küçük kabul edilir.

Dizi baştan sona kadar ilk elemandan küçük olan elemanı bulana kadar kontrol edilir.

Eğer aramada daha küçük bir sayı bulunduysa onu alır en başa yerleştirir.İlk terimide onun yerine konur.

Daha sonra aynı işlem sırasız olan alt dizin için sürekli aynı adım uygulanır.

Sıralamaya kalan altdizinler bitene kadar devam edilir.Sol taraf sıralı bir altdizi, sağ taraf sırasız bir alt dizi oluşur.



Sırasız altdizi bitince kadar sıralama devam edilip bitirilmiş olunur.

Selection Sort(Seçerek Sıralama)’un nasıl çalıştığını örneklerle inceleyelim.
![image-center]({{ '/images/SelectionSort/Selection-Sort-java-sıralama.gif"' | absolute_url }}){: .align-center}

![image-center]({{ '/images/SelectionSort/secerek-sıralama-selection.jpg' | absolute_url }}){: .align-center}

![image-center]({{ '/images/InsertionSort/Selection-Sort-Seçerek-Sıralama.gif' | absolute_url }}){: .align-center}

![image-center]({{ '/images/InsertionSort/Selection-Sort-Seçerek-Sıralama.gif' | absolute_url }}){: .align-center}

![image-center]({{ '/images/InsertionSort/selectin-sort-çalışma-mantığı-psuedo.gif' | absolute_url }}){: .align-center}

#### Selection Sort(Seçerek Sıralama)’un Algoritma Karmaşıklığı

Worst Case(Ters Dizi):O(n^2)
Best Case (Sıralanmış Dizi):O(n)
Average Case(Ortalama):O(n^2)

#### Selection Sort(Seçerek Sıralama) JAVA Kodu

