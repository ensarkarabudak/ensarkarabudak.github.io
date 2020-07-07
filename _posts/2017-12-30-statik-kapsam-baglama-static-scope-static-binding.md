---
layout: post
title: "Statik Kapsam Bağlama(Static Scope,Static Binding)"
tags:
  - programlama dilleri
  - bilgisayar bilimleri
---

{% include responsive-embed url="https://www.youtube.com/embed/WNlJFz65vRo" ratio="16:9" %}

Statik Kapsam Bağlama,**yerel olmayan** değişkenleri bağlamak için dinamik kapsam bağlama kullanılır.
Değişkenlerin kapsamları,programın metinsel düzenine göre belirlenir.Yani bulundukları konumlara göre.
Bir değişkene olan başvuru, programın çalıştırılması gerekmeden, program metninin incelenmesi ile belirli bir değişken tanımına bağlanabilinir.

![image-center]({{ '/images/StatikScope/Static-Binding-ornek.png' | absolute_url }}){: .align-center}

Statik kapsam bağlamayı sağlayan diller iç içe alt programları desteklerken(Ada, JavaScript, PHP),
bazı programlama dilleri desteklemez(C,C++).Statik kapsamı çevreleyen kapsam onun atasıdır.En yakın ataya, ebeveyn (parent) denir.

Aşağıda Pascal dilinde yazılmış bir statik kapsam bağlama örneği bulunmaktadır.

![image-center]({{ '/images/StatikScope/Static-Scope-Static-Binding.png' | absolute_url }}){: .align-center}

Bir program birimi içinde tanımlanmış değişkenler,o birim için yerel değişkenlerdir.
O program birimi içinde görünür olan,ancak o birimde tanımlanmamış değişkenler ise yerel olmayan değişkenler olarak adlandırılmaktadır.

#### Statik Kapsam Bağlama Örneği

![image-center]({{ '/images/StatikScope/statik-scope-ornegi-1.png' | absolute_url }}){: .align-center}

#### Video’daki Statik Kapsam Bağlama Örneği

```
program main;var x,y,z:integer;procedure sub1;var a,y:integer;begin(sub1)a=x+z+10;y=100;x=a+20;end(sub1)
procedure sub2;
var a,x:integer;procedure sub3;
var a,z:integer;
begin(sub3)stat
a=y;
x=a+10;
z=500;
call sub1;
y=x-z;
end(sub3)
begin(sub2)a=5;call sub3;z=z+x+100;end(sub2)begin(main)x=77;y=77;z=x+y;call sub2;print x,y,z;end(main)
```