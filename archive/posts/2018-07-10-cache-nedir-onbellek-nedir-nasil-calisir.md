---
layout: post
title: "Cache Nedir? Önbellek Nedir? Nasıl Çalışır?"
---

#### Önbellek(Cache) Nedir?

Günümüz bilgisayar işlemcileri(CPU) çok hızlıdır ve sürekli olarak **hafızadan(RAM)** veri okur.Hafıza,İşlemciye göre yavaş çalışan bir birim olduğu için işlemci RAM’i beklemek zorunda kalır.Bu durumu çözen birime biz **Önbellek(Cache)** Diyoruz.İşlemci içinde çok yüksek hızlı çalışırlar.

#### Cache Nasıl Çalışır?

Hafıza gibi adresleme ile çalışmaz doğrudan **içeriklerle** erişilir. Bu nedenle verilerin yerinin bellekte işlemini basitleştirmek için pek çok önbellek ile veri arasında eşleme algoritması kullanılır.

#### Önbellek(Cache) Çeşitleri Nelerdir?

**#L1 önbellek(cache):**Önemli program kodları ve program verileri bellekten yani RAM’den buraya kopyalanır.Kapasitesi:2 KB-256 KB

**#L2 önbellek(cache):**Kapasiteleri 256 KB ile 2 MB arasında değişir.L1 önbelleklere göre acil olmayan işlemler üzerinden veri aktarımı yapar.

**#L3 önbellek(cache):**Kapasiteleri 2MB ile 256 MB arasında değişir.Yeni anakartlarda kullanılan bir teknolojidir. Çok çekirdekli işlemcilerde kullanılmak üzere tasarlanmıştır.

#### Web Üzerinde Cache Kullanımın Önemi Nedir?

Uygulamar veya web siteleri üzerinde yaptığımız işlemlerde veri tabanlarında tuttuğumuz verileri alıp kullanmak için belirli bir **zaman ve işlem maliyeti** harcıyoruz.Bu maliyet hem kullanıcı hem de geliştirici tarafından **dezavantaj** sağlıyor.

Web üzerinden gelen çok istekli bir ortamda yığılmalara sebebiyet veriyor.Buda sunucudaki **CPU-RA**M arasındaki kızışmayı tetikliyor.Burada Cache yani önbellek devreye girerek iki tarafıda(CPU-RAM) sakinleştiriyor.Bir örnek verecek olursam,örneğin bir web sitesine ikinci bir defa girdiğinizde önceden girdiğiniz verileri **cache bellekte** tutarak başta söylediğim maliyetten kendinizi kurtarmış olursunuz.

#### Nasıl Bir Cache Mekaznizması Olmalı?

Eğer sunucu tarafında kullanılan yazılım süreçlerine hakim değilseniz veya sisteminizde **SSD yerine hard disk**kullanımı mevcut ise ve bunu bilmiyorsanız seçeceğiniz cache(önbellek) sizi yarı yolda bırakabilir.
Yani sisteminizde hafıza birimi mutlaka SSD tarzı bir hafıza kullanmalısınız.Bu cache açısından oldukça önemli bir adım olacaktır.Hızlı hafıza birimi sayesinde kullanıcıdan gelecek veriyi oldukça kolay işleyebilirsiniz.

**#**Disk ve CPU kullanımı minimize edilmeli.
**#**Veriler RAM üzerinde tutulmalı.(Bunun sebebi query(sorgu),bazı veri tabanı tablo yapıları gibi veriler RAM üzerinde tutulabiliyor)

#### Önbellek(Cache) Katmanları

**Veri tabanında:**MySQL InnoDB, query cache vb.

**Yazılım tarafında:**Memcache,redis,varnish,sphinx,elasticsearch vs.

Bunların dışında web sunucularınızda yapacağınız yazılımla kullanıcının tarayıcısında bulunan önbellekleri kullanabilirsiniz.Bunlar:etag,max age vs.

#### Bilgisayar Cache(Önbellek) Kapasitelerini ve Bilgilerini Nasıl Öğrenebilirim?

`lscpu`
Komutuyla Önbellek ve CPU bilgilerinizi öğrenmebilirsiniz.