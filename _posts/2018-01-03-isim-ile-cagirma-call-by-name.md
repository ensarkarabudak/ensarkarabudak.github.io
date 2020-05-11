---
layout: post
title: "İsim ile Çağırma(Call by Name)"
tags:
  - programlama dilleri
  - bilgisayar bilimleri
---

İsim ile Çağırma(Call by Name)

İsim ile çağırma yöntemi de bir içeri-dışarı modeli için gerçekleştirimidir.
Bir gerçek parametre isim ile çağırma yöntemi ile aktarıldığında,altprogramda gerçek parametreye karşı gelen resmiparametrenin bulunduğu her yere metinsel olarak gerçek parametre yerleştirilir. 
Eğer gerçek parametre bir sabit değerse, isim ile çağırma yöntemi, değer ile çağırma yöntemi ile aynı şekilde gerçekleşir. 
Eğer gerçek parametre bir değişkense, isim ile çağırma yöntemi başvuru ile çağırma yöntemi ile aynı şekilde gerçekleşir.



### İsim ile Çağırma Örneği

void f(int a,int b)
{
b=5;
b=a;
}

int g()
{
int i = 3;
f(i+1,i);
write i;
}
Çıktı: 6 Olacaktır.