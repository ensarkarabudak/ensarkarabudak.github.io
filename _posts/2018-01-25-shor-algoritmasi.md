---
layout: post
title: "Shor algoritması(Shor’s algorithm)"
---

**Shor algoritması**,kuantum bilgisayarlarda kullanılan çok büyük sayıda sayıları çok kolay bir şekilde sayıyı asal çarpanlarına ayıran bir algoritmadır.Bu algoritmanın kullanımı oldukça önemlidir çünkü **açık anahtar şifrelemesini**kullanan sistemleri kolayla kırılabilir.
Örneğin, **RSA**,iki büyük asal sayıdan oluşan bir genel anahtar N kullanır.RSA şifrelemesini kırmanın bir yolu, N’yi çarpanlara ayırmaktır;ancak klasik algoritmalarla, faktoring, N büyüdükçe giderek zaman alıcı hale gelir ; Daha spesifik olarak, herhangi bir k için O ((log N ) k ) zamanını etkileyebilecek klasik bir algoritma bilinmemektedir . Buna karşılık, Shor’un algoritması, RSA’yı polinom zamanında çatlatabilir. Birçok diğer ortak anahtarlı şifreleme sistemine saldırmak da uzatıldı.
**Kuantum Fourier Transform** formülünü kullanarak RSA sistemleri **polinomsal** zamanlarda çözebilen qubitler üzerinden çalışalarak **250** rakamlı bir sayıyı asal çarpanlarına ayırması 2 gün sürmüştür.

Shor algoritması iki bölümden oluşur:

1-Faktoring probleminin , klasik bir bilgisayarda yapılabilen sipariş bulma problemine indirgenmesi .
2-Sipariş bulma problemini çözmek için bir kuantum algoritması.

### Shor Algoritmasına Yapılan Değişiklikler

Shor’un algoritmasına birçok değişiklik yapılmıştır. Örneğin, Shor’un özgün algoritması durumunda bir kuantum bilgisayarda bir yirmi ila otuz kez bir sıralama gerekirken, diğer bazı değişikliklerle birlikte, David McAnally tarafından **Queensland Üniversitesi**‘nde yapılan değişiklik durumunda kuantum bilgisayarda sadece dört ila sekiz sıraya ihtiyaç vardır.