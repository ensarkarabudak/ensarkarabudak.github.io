---
layout: post
title: "Radix Sort(Taban Sıralaması)"
---

Radix Sort(Taban Sıralama),tamsayı bulunduran dizileri küçükten büyüğe ya da büyükten küçüğe sıralı bir şekilde sıralayabilecek bir metottur.Radix Sort(Taban Sıralama),sayıları basamakları üzerinde işlem yaparak sıralayan algoritmalarından biridir.Radix Sort algoritması,aslında 2’lik tabana göre geliştirilmiş hızlı bir şekilde sıralayan algoritmadır.Radix Sort,taban sıralama veya hane sıralaması olarak isimlendirilir.



#### Radix Sort(Taban Sıralama) Örneği

Dizimiz şu şekilde olsun:
**170, 45, 75, 90, 802, 24, 2, 66**

1.Adım
Birler basamağına göre sıralayacağız.

**170, 90, 802, 2, 24, 45, 75, 66**

2.Adım
Onlar basamağına göre sıralayacağız.

**802, 2, 24, 45, 66, 170, 75, 90**

3.Adım
Yüzler basamağına göre sıralayacağız.

**2, 24, 45, 66, 75, 90, 170, 802**

Böylelikle sıralanmış diziyi elde edilir.

![image-center]({{ '/images/RadixSort/Radix-SortTaban-Sıralama.png' | absolute_url }}){: .align-center}
