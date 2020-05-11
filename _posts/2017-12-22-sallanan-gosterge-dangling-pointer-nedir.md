---
layout: post
title: "Sallanan Gösterge(Dangling Pointer) Nedir?"
tags:
  - bilgisayar bilimleri
---

**Sallanan Gösterge**,bir göstergenin(pointer) gösterdiği değişkenin adresinde veri olmaması durumudur.Yani pointer(gösterge) serbest bırakılmış bir yığın değişkene işaret etmiş olur.Serbest bırakılmış bir bellek adresini gösteren göstergeye sallanan gösterge (dangling pointer) denir.

C ve C++’da da sallanan gösterge sorunu vardır.C’de sallanan gösterge oluşumu aşağıdaki şekilde görülmektedir.

##### C sallanan gösterge (dangling pointer) örneği:

```
int *pointer1,*pointer2;....pointer1=mallac(sizeof(int));pointer2=pointer1;free(pointer1);
```

Başka bir sallanan gösterge (dangling pointer) örneği:

```
int *pointer (){int deger = 42;return & deger;}int* p = pointer();*p = 0;
```

Yukarıdaki kod gösterici dönen pointer’i çağırır,sonucu bir gösterici değişkene koyar, sonra bunu değiştirmeye çalışır.

Fakat göstericinin gösterdiği deger pointer’nin içinde tanımlıdır, deger’in yaşamı bitince onun bellekte kullandığı yer de iade edilmiştir, bu şekilde kullanılması beklenmedik sonuçlar doğurur.
Java programla dilinde ise pointer veri tipine dilde yer verilmeyerek,güvenlilik sağlanmıştır.