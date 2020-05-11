---
layout: post
title: "Başvuru ile Çağırma(Call by Reference)"
---

Başvuru ile Çağırma(Call by Reference)

Başvuru ile çağırma yöntemi de gerçek ve resmi parametreler arasında iki yönlü veri aktarımı sağlar.
Ancak önceki yöntemlerden en önemli farkı, altprograma verinin adresinin aktarılmasıdır.

Bu adres aracılığıyla altprogram, çağıran program ile aynı bellek yerine erişebilir ve gerçek parametre,
çağıran program ve altprogram arasında ortak olarak kullanılır.



### Başvuru ile Çağırma Örneği

y: integer;
procedure p(x: integer)
{ x := x + 1;
x := x + y;
}
…
y := 2;
p(y);
write y;

Çıktı:5 Olacaktır.

### Başvuru ile Çağırma Örneği-2

x : integer;
procedure foo(y : out integer)
y := 3;
print x;
. . .
x := 2;
foo(x);
print x;

Çıktı:3 3 Olacaktır.