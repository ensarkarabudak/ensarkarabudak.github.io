---
layout: post
title: "Kablosuz Ağlarda Güvenlik"
---

Kablosuz ağlarda veri iletimi herhangi bir fiziksel ortam olmaksızın havadan gerçekleştiği için verilerin 3.şahısların tarafından ele geçirilmesi ve takip edilmesi mümkündür. Bu nedenle kablosuz ağlarda güvenlik önemli bir konudur.

Kablosuz ağlara izinsiz erişim sağlamaya çalışan temel 3 grup vardır. Bunlar; meraklı kullanıcılar, başkasının internetini kullanmak isteyen kullanıcılar ve **hacker’lar**.

Meraklı kullanıcılar, ağ açısından çok fazla tehdit oluşturmaz ama sürekli karşılaşılacak kullanıcı grubudur. Özellikle güvenlik hakkında bilgi sahibi olmayan ve hazır araçlar yardımıyla ağa girmeye çalışan kulianıcılardır. Bu nedenle yapabilecekleri sınırlıdır. Bu tür kullanıcılardan korunmak için **SSID** gizleme ve **MAC filtreleme** yeterli olacaktır.

Kablosuz internetinizi ortak kullanmak isteyen kullanıcılar ise yeterli ve düzgün yapılandırılmamış kablosuz ağlara erişmeye çalışır. Bunların temel amacı internet erişimi olduğu için ağa zarar vermeden ağı kullanmaya devam eder.

**Hacker’lar** en tehlikeli kullanıcı grubu olup ağ üzerindeki bilgilerin elde edilmesi veya ağa zarar vermek gibi amaçları olabilir. Bu tür kullanıcılardan korunmak için en temel güvenlik önlemi ise WEP/WPA protokolleri ile ağa erişimi ve ağ üzerindeki trafiği şifrelemektir.

#### SSID Gizleme

**SSID** kablosuz bir ağda erişim cihazı olarak görev yapan cihazın kablosuz ağa Verdiği isimdir. Yani kullanıcılar ağa erişmek istediğinde SSID ‘ile belirlenen ism; görür ve bağlanır. Bir WLAN’ın güvenli hale getirmenin en temel basit yöntemi kablosuz erişim cihazının herkese dağıtım yapmasını engellemektir. Yani SSID bilgisini gizli konuma getirmektir. Bu durumda ağa sadece SSID ismini bilen kullanıcılar bağlanabilir. Ancak SSID saklama tam bir güvenlik sağlamayıp acemi düzeydeki kullanıcılardan koruma sağlar. SSID saklansa dahi yine gizli olarak ve SSID bilgisini şifrelemeden yayın yapmaya devam eder. Bu da kötü niyetli bir kullanıcının özel araçlar ile gizli SSID bilgisini kolaylıkla tespit etmesini sağlar.

#### Erişim Şifresi

Diğer bir güvenlik yöntemi SSID’si bilinen veya çeşitli yöntemlerle tespit edilen bir ağa erişim sağlanmak istendiğinde kullanıcıdan giriş anahtarı (şifre) istenmesidir. Giriş anahtarı için **WPA, WEP** gibi şifreleme teknikleri kullanılabilir.

#### WEP (Wired Equivalent Privacy Kabloya Eş Güvenlik)

Kablosuz ağlarda veri şifreleme ve doğrulamayı gerçekleştirir. Paylaşılmış **gizli anahtar** mantığına dayalıdır. Bu anahtar veri paketlerini göndermeden önce şifrelemek ve bunların veri bütünlüğünü kontrol etmek için kullanılır. Ağa giriş anahtarını bilen herkes kablosuz ağa dahil olabilir. WEP’te her şeyden önce kullanılan şifre uzunluğu ve belirlenen şifre önemlidir. Şifre ne kadar uzunsa o kadar sağlamdır. WEP günümüzde 128 bit şifreleme sağlamaktadır. 128 bit WEP şifrelemede belirlenecek şifre S ile 13 arası karakterden oluşur. Bir diğer nokta ise belirlenen şifrenin rasgele aralıklarla değiştirilmesidir.

#### WPA (Wi-Fi Protected Access Wi-Fi Korumalı Erişim)

WEP’de çıkan güvenlik açıklarının giderilmesi ve yeni özelliklerin eklenmesi ile çıkarılmış güvenlik protokolüdür. En az **8 karakterlik** şifre belirlenmelidir. 1 bitlik veri üzerinde dahi şifreleme anahtarları kullandığı için verilere ulaşarak **izinsiz** değiştirmek isteyen kullanıcıların verileri değiştirmesini engeller. WPAZ (Wi-Fi Protected AccessZ) şifreleme WPA’nın devamı niteliğindedir. Ağa sadece yetkili kişilerin girebileceği konusunda güven vermektedir. WPAZ’nin iki sürümü mevcuttur: WPAZ-Personal(Kişisel) ve WAZ-Enterprise (Kuruluş). WPAZ-Personal yetkisiz kişilerin ağlara girişini bir kurulum şifresi kullanarak engellemeyi amaçlar. WPAZ-Enterprise ise ağ kullanıcılarını bir sunucu yardımıyla denetler.

WPA ve WPAZ kişisel sürümü ev ve küçük oüsler gibi kimlik doğrulama sunucuları olmayan kullanıcılar için tasarlanmıştır. Kimlik doğrulama için **IEEE 802.1X** yerine Önceden paylaşımlı bir şifre kullanır. WPA-WPAZ kişisel sürümü WPA-WPAZ Enterprise sürümü ile aynı şifreleme yöntemlerini kullanır. WPA, TKlP yoluyla
WPAZ ise AES yoluyla kullanıcı, oturum, paket başına şifrelemeyi destekler.

#### MAC Filtreleme

Bir diğer güvenlik yöntemi ise kablosuz ağa erişecek cihazların MAC adreslerinin belirlenmesi ve bunlar dışında MAC adresine sahip cihazlardan gelecek ağa erişim istekleri reddedilecektir. Ancak deneyimli ve kablosuz ağa girmek isteyen bir kullanıcı, veriler havadan iletildiği için kablosuz ağ ile iletişime geçebilecek MAC adreslerini tespit ederek kendi MAC adresini bu adreslerle değiştirerek ağa erişebilir.

#### VPN Tunel

Kablosuz ağların büyük çoğunluğu kablolu ağlara **Access Point** eklenmesiyle elde edilmektedir. Bu tür ağlarda kablolu ağ ile kablosuz ağ arasına bir güvenlik duvarı eklenerek her iki ağ için de güvenlik sağlanabilir. Alınan bu güvenlik önleminin de yeterli olmadığı durumlarda iki ağ arasına (kablolu ve kablosuz) güvenlik duvarı yerine VPN [Virtual Private Network Sanal Özel Ağ] yerleştirilerek veri geçişi bunun üzerinden sağlanabilir. Bu iş için WLAN ve mevcut LAN arasında duracak olan bir VPN-Ağ-Geçidine ihtiyaç duyulur. Mevcut ağa erişim isteyen tüm makineler de VPN istemcilerinin kurulu olması gerekecektir. Böylece LAN’a ulaşmanın tek yolu VPN tüneli üzerinden gerçekleşecek.