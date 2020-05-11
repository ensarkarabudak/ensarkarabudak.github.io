---
layout: post
title: "Dinamik Kapsam Bağlama(Dynamic Scope,Dynamic Binding)"
tags:
  - programlama dilleri
  - bilgisayar bilimleri
---

<center>
<iframe width="720" height="315" src="https://www.youtube.com/embed/CcWNsJoKlws" frameborder="0" allowfullscreen></iframe>
</center>

Dinamik kapsam bağlama,bir ismin kapsamının,yordamların fiziksel olarak yakın olmalarına göre değil,
yordamların çağrılma sırasına göre belirlenmesidir.Çalışma zamanında gerçekleşir.
Dinamik kapsam bağlamada bir ismin tanımı,çalışma sırasında aynı isimde bir başka tanımlama bulunana kadar,kedisinden sonra çalıştırılan tüm komutlarda geçerlidir.
Avantaj olarak,elverişliliği sağlar.Dezavantaj olarak okunabilirliği azaltır.

### Dinamik Kapsam Bağlama Örneği

![image-center]({{ '/images/DinamikScope/Dinamik-Scope-ornegi.png' | absolute_url }}){: .align-center}

### Dinamik Kapsam Bağlama Örneği

![image-center]({{ '/images/DinamikScope/dinamik-scope-ornegi.png' | absolute_url }}){: .align-center}

#### Video’daki Dinamik Kapsam Bağlama Örneği

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