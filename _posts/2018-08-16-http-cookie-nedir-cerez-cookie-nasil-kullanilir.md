---
layout: post
title: "Http Cookie Nedir ? – Çerez(Cookie) Nasıl Kullanılır ?"
---

Cookie(Çerezler), kullanıcıların bilgisayarında bulunan, web sitesinin içinde bulundurduğu bilgileri saklarlar.Tarayıcı cookie’yi alır ve sunucuya gönderdiği bütün istekleri HTTP header’larına ekler. Böylece sunucu session bilgisini alır buna **session cookie** denir.

Web sitelerin büyük çoğunluğu kullanıcıların giriş bilgilerini saklayarak kullanım kolaylığı sağlamak için kendi bilgisayarında cookie ‘ler oluşturur. Birkez daha aynı siteyi ziyaret girildiğinde tarayıcılar bunu *HTTP Request* mesajının header’ı içinde web sunucuya gönderir.

Cookie’ler(Çerezler) bilgisayardaki bilgileri erişimi web sunucunun o bilgisayardaki tüm dosyalara erişeceği anlamına gelmez.Sunucu böyle bir cookie oluştur/sil/değiştir diye bir bilgi veriyor tarayıcıya,tarayıcımız da bu işlemleri kendisi gerçekleştiriyor.İsterseniz bunu kullandığınız tarayıc

Her bir websitenin kendine ait cookie’si olabileceği gibi aynı sitenin birden fazla cookie si olabilir.

#### Cookie Nasıl Oluşturulur?

Cookie sunucunun yönetimindedir. Cookie nin oluşmasını sunucu belirliyor. [TCP 3’lü el sıkışma](http://ensarkarabudak.com/bilgisayar-aglari/tcp-uclu-el-sikisma-tcp-3-way-handshake/)nın başarıyla olduğunu ve HTTP Request gönderildiğini düşünelim. Her şey başarılı gerçekleşti ve sunucu bir başarılı HTTP Response mesajı göndersin yani **HTTP/1.1 200** **OK** mesajını gelsin.

Tarayıcı **set-cookie** header ını görürse bu şu anlama geliyor:Sunucu bir cookie oluşturmak istiyor tarayıcıdan ve tarayıcı da cookie oluşturuyor. Artık girdiğimiz web sayfasına tekrar girdiğimizde tarayıcımız sitenin cookie si var mı yok mu kontrol ediyor, var ise bundan sonraki tüm HTTP Request isteklerini bu cookie i sunucuya gönderiyor. 

#### Cookie’lerin Özellikleri

Cookie’lerin birkaç özelliği bulunur.Bunlara bakalım.

- **expires**: Cookie’nin tarayıcımız üzerinde ne zaman sonlanacağını belirtiyor.Verilen tarih ve saat bilgisiyle süre geldiğinde cookie silinir. Bu parametre verilmezse cookie ler tarayıcı açık olduğu müddetçe tutulur.
- **domain**: Cookie’nin hangi domainlere üzerinde çalıştığını ve ait olduğunu belirtiyor. Eğer belirtilmezse cookie nin alt domainlerinde aktif olmaz.
- **path**: Bu parametre de cookie nin domain üzerinde bulunun hangi adres yolu üzerinde aktif olacağını belirtir.

> JavaScript Cookie Oluşturma
>
> ```
> document.cookIe = "name=ensar; expıres=wed, 12 Dec 2018 13:05:38 UTC; path=/";
> ```

### HttpOnly

Javascript cookie leri değiştirebilen bir betik dildir.Bu büyük bir güvenlik açığı oluşturuyor. XSS zafiyeti sayesinde cookie ler ele geçirebilir.Cookie oluştururlen “**HttpOnly**” flag ini aktif ederseniz cookie ler javascript ile erişilemez hale gelir.

### Secure

Cookie lerin güvenlik ile alakalı bir diğer yer ise  Secure bayrağında bulunuyor.Bu flag aktif edilirse cookie güvenliksiz  http bağlantılarında gönderilmiyor, sadece ssl/tls sertifikası bulunan yani **https** sayfalarında gönderiliyor Buradaki açıktan faydalanan saldırgan cookie lerinizin  ele geçirilmesini önlüyor.