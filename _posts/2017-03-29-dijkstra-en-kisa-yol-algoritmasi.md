---
layout: post
title: "Dijkstra En Kısa Yol Algoritması (Dijkstra’s Shortest Path Algorithm)"
tags:
  - algoritma
---

{% include responsive-embed url="https://www.youtube.com/embed/X2dJI-S35ck" ratio="16:9" %}

Dijkstra algoritması,**ağırlıklı bir graf üzerinde** yani kenarları(edge) belli bir metrik değere göre değerleri olan herhangi iki düğüm arası en kısa mesafeyi bulmamızı sağlayan bir algoritmadır.

Algoritma,Hollandalı matematikçi ve bilgisayar bilimci **Edsger Wybe Dijkstra** tarafından bulunmuştur.Bu algoritma routing başta olmak üzere birçok alanda kullanılmaktadır.Hatta birçoğumuzun telefonlarında veya diğer teknolojik cihazlarında bulunan navigasyonun temeli bu algoritmaya dayanır.

En kısa yol problemlerini çözmek için geliştirilen diğer algoritmalar:**Bellman Ford** ve **Floyd** algoritmalarıdır.

**Dijkstra algoritmasını kullanmamız için;**

Grafımız ağırlık ve yönlü olmalı.

Kenarların ağırlık değeri sıfır ya da sıfırdan büyük bir değer olmalıdır.

Eğer kenar değerleri sıfırdan küçükse Bellamn-Ford algoritması kullanılabilir.

Dijkstra algoritmasını zaman karmaşıklığı yani büyük o notasyonu **O(MlogN)**‘dir.

Dijkstra algoritması Aç gözlü yani **Greedy** bir algoritmadır.
Yani dijkstra algoritması,bir düğümden diğer bir düğüme geçerken mevcut durumun ‘en iyi’ çözümünü seçer.

Bir örnek üzerinde **dijkstra algoritmasın**ı anlatmaya çalışalım.

Algoritmanın başlangıç düğümü(node) **A** olsun.A düğümü henüz hiçbir düğüme erişim olmadığını kabul ederek her bir düğüme ulaşımı sonsuz(∞) değeri atarıyoruz.

![image-center]({{ '/images/dijkstra-algorithm-1.jpeg' | absolute_url }}){: .align-center}

Daha sonra başlangıç düğümünün komşusu olan bütün düğümlere giderek mesafemizi güncelliyoruz.Burada ‘b’ ve **‘c’** düğümlerine erişim sağlıyor.

![image-center]({{ '/images/dijkstra-algorithm-2.jpeg' | absolute_url }}){: .align-center}

A düğümüyle işlemimiz bitti.Şimdi sıra farketmeksizin yani **ister** ‘b’ **ister** ‘c’ düğümünden başlayarak tıpkı ‘a’ düğümünde yaptığımız gibi mesafeleri güncellememiz gerekmektedir.C düğümünden başlayalım ilk güncellememize.

![image-center]({{ '/images/dijkstra-algorithm-3.jpeg' | absolute_url }}){: .align-center}

Şimdi burada **dikkat edilmesi gereken husus** a-b arası 4 birim uzaklıktaydı.Artık C düğümünü güncellediğimiz için a-b düğümleri arasını c üzerinden(a-c-b) gidersek 3 birim uzaklıkta olduğu için ‘b’ düğümüne ulaşımımız 3 olarak güncellemimiz gerekiyor.

![image-center]({{ '/images/dijkstra-algorithm-4.jpeg' | absolute_url }}){: .align-center}

Sıra geldi ‘b’ düğümünün komşu düğümlerini güncellemeye.
Komşu olarak c ve d düğümleri var.C düğümüne ulaşımımız a-b-c üzerinden
4+1=5 birim ama biz a-c arası mesafemiz 2 olduğu için güncellememize gerek yoktur.Çünkü daha fazla maliyetlidir.

B düğümünün diğer komşusu olan d düğümüne mesafesi a-b-d üzeriden 4+3=7’dir.Diğer görselde a-c-d mesafesi 2+8=10 olduğu için **güncellememiz gerekecektir.**

![image-center]({{ '/images/dijkstra-algorithm-5.jpeg' | absolute_url }}){: .align-center}

Şimdi ‘d’ düğümünün komşularına bakalım.E düğümüne a-c-e üzerinden ulaşım 10+2=12 birim uzaklıktaydı fakar a-c-b-e üzerinden ulaşım **2+1+5+2=10** birim uzaklıkta olacaktır. ve ‘e’ düğümüne bundan başka daha az mesafede ulaşamayız.

![image-center]({{ '/images/dijkstra-algorithm-6.jpeg' | absolute_url }}){: .align-center}

E düğümünün komşu düğümlerini güncelleyelim.Komşu düğüm olarak güncellememiz gerek tek düğüm kaldı o da ‘z’ düğümü.Bir önceki örnekte d üzerinden maliyetimiz 8+6=14 idi.fakat ‘e’ düğümü üzerinden 10+3=13 birim uzaklıkta olduğu için güncellememiz gerekecektir.

![image-center]({{ '/images/dijkstra-algorithm-7.jpeg' | absolute_url }}){: .align-center}

artık mesafe olarak güncellememiz gereken bir düğüm kalmadığı için algoritma bu graf için sonlanır.

> Bu algoritmanın amacı:Bir düğümden başlayarak o düğümün tüm graf üzerinde bulunan düğümlerine en kısa mesafede ulaşmasını garanti eder.Ayrıca bundan daha kısa bir yol bulunmayacağını iddia eder.Eşit mesafe olabilir.

Biz bu graf için **‘a’ düğümünün graf üzerindeki tüm düğümlere en kısa mesafede gitmesini** inceledik.

Dijkstra algoritmasının dezavantajı

Bu algoritma eksi(-) değer taşıyan kenarlar üzerinden sağlıklı bir şekilde çalışmaz.Aksi takdirde sürekli olarak mevcut durumdan daha iyi bir sonuç üretmesine yol açar buda algoritmayı sonsuz bir döngü içine sokabilir.