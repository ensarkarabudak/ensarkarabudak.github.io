---
layout: post
title: "Bellek Sızıntısı"
tags:
  - bilgisayar bilimleri
---

![image-center]({{ '/images/bellek-sizintisi.png' | absolute_url }}){: .align-center}


Şekil: Verilen program parçası için belleğin durumu.
(a) a satırındaykenki durum.
(b) b satırındaykenki durum.
(c) c satırındaykenki durum.

```
class Node {int value;Node *next;};
...
Node *p = new Node();
Node *q = new Node();
Node *r = new Node();
p->next = q;q->next = r; // ar = NULL; // bdelete q; // c
```

Yukarıda verilen program parçasının a satırına kadar işletilmiş olduğunu düşünelim. Buna göre belleğin şu andaki durumu Şekil a’daki gibi olacaktır. Bu durumda tüm nesnelere programın bağlamındaki değişkenlerden (statik ya da yığındaki değişkenlerden) ulaşmak mümkündür.

B satırına gelindiğinde r değişkenine NULL atanarak r ile işaret ettiği nesne arasındaki bağlantı koparılır. Son olarak c satırında q’nun işaret ettiği nesnenin kapladığı alan bellek yöneticisine geri verilir.

Bu anda iki sorun ortaya çıkar:
\1. Artık q’nun ve p->next’in işaret ettiği bellek bölgesi bellek yöneticisine geri verildiği için geçersizdir. Bu yüzden q’ya ve p->next’e geçersiz işaretçiler deriz.

\2. Eskiden r’nin işaret ettiği nesneye artık bağlamdan ulaşmanın bir yolu kalmamıştır. Bu tür nesnelere çöp denir. Çöp nesnelerin bellekte gereksiz alan kaplamasına da **bellek sızıntısı** denir.