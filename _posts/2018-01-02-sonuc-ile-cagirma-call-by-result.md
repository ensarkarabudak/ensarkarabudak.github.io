---
layout: post
title: "Sonuç ile Çağırma(Call by Result)"
tags:
  - programlama dilleri
  - bilgisayar bilimleri
---

Sonuç ile Çağırma(Call by Result)

Sonuç ile çağırma yöntemi, dışarı modelinin gerçekleştirimidir.
Bu yöntemde çağırım deyimi ile altprograma bir değer aktarılmazken,gerçek bir parametreye karşı gelen resmi parametrenin değeri, altprogram sonunda, denetim yeniden çağıran programa geçmeden önce, gerçek parametreyi gösteren değişkene aktarılır.

![image-center]({{ '/images/sonuc-ile-cagirma.png' | absolute_url }}){: .align-center}

Bu tanımlamadan anlaşıldığı gibi,gerçek parametrenin değişken olması zorunludur.
Gerçek parametreye karşı gelen resmi parametre, altprogramın çalışması süresince yerel değişkendir. 
Bu yöntemin uygulanmasındaki güçlük, gerçek parametrenin değerinin resmi parametreye aktarılmasının
önlenmesidir.



### Sonuç ile çağırma örneği

void plus(by-value int a, by-value int b, by-result int c)
{
c = a+b;
}

void f()
{
int x = 3; int y = 4; int z;
plus(x, y, z);
write z;
}

Çıktısı:7 Olacaktır.