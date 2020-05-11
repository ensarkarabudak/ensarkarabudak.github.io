---
layout: post
title: "Sezar Şifrelemesi(Caesar Crypto)"
tags:
  - kriptoloji
  - bilgisayar bilimleri
---

Bu şifreleme adını Julious Ceasar’dan alan basit bir yer değiştirme şifreleme örneğidir.
Şifrenin oluşturulması şu şekilde:Her harf,belirli bir kaydırma dönüşümü kullanılarak
elde edilen başka bir harf ile değiştirilir.İki karakter kümesi ya da alfabesi,açık metin ve şifreli metin için oluşturulmuştur.

##### Sezar Şifrelemesi Örneği

Örnek:

Açık metin alfabesi:

A B C Ç D E F G Ğ H I İ J K L M N O Ö P R S Ş T U Ü V Y Z

Şifreli metin alfabesi:

EFGĞHIİJKLMNOÖPRSŞTUÜVYZABCÇD

Mesajın şifrelenmesi sırasında örneğin,açık metindeki A,E ile E ise I ile yer değiştirir.
Bu durumda açık metin “GÖZ KALBİN AYNASIDIR” şifrelendiğinde,**“JTD ÖEPFNS EÇSEVMHMÜ”** şifreli metni oluşur.

Sezar şifresini oluşumundan sonra kullandığımız her sembol aslında bir başka sembolün haritasını oluşturur.Bu sisteme yerine koyma adı verilir.Güvenli görülebilir Türkçe için **29!** olası anahtar vardır.bu olasılıkların denenmesi yıllarca sürebilir fakat Türkçede en sık kullandığımız harflerin **‘a’** ve **‘e’** olduğunu bildiğimizden küçük kelimeler için oluşturulmuş bir mesaj parçası için şifreyi çözmek kısa zaman alır.