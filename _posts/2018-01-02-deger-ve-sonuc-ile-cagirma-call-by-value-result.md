---
layout: post
title: "Değer ve Sonuç ile Çağırma (Call by Value Result)"
---

Değer ve Sonuç ile Çağırma (Call by Value Result)

Değer ve sonuç ile çağırma yöntemi, içeri-dışarı modelinin gerçekleştirimi olup,değer ile çağırma ve sonuç ile çağırma yöntemlerinin birleşimidir.

Bu yöntemde, gerçek parametrenin değeri ile karşı gelen resmi parametrenin değeri bağlandıktan sonra resmi parametre,altprogramın çalışması süresince yerel değişken gibi davranır ve altprogram sona erdiğinde resmi parametrenin değeri
gerçek parametreye aktarılır.Bu yöntemde de gerçek parametrenin değişken olması zorunludur.



### Değer ve Sonuç ile Çağırma Örneği

m,n : integer;

procedure r (k,j : integer)
begin
k := k+1;
j := j+2;
end r;
…
m := 5;
n := 3;
r(m,n);
write m,n;

Çıktısı:6 5 Olacaktır.