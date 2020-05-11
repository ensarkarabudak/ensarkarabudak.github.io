---
layout: post
title: "Proxy Server Nedir?,Vekil Sunucu Nedir?"
---

Proxy Server(Vekil Sunucu)

İnternet erişimi sırasında kullanılan bir ara sunucudur. internete erişecek bilgisayar proxy server üzerinden çıkış yapar. Böylece çok fazla ziyaret edilen bir sayfa **proxy server** önbelleğine alınarak istekte bulunan bilgisayara önbelleğinden web sayfasını göndererek erişim hızını artırır. Ayrıca erişimi yapılacak sayalara yasak getirerek kullanıcıların sayfaya erişimini engelleyebilir veya uygunsuz içerik içeren sayfaların uygunsuz bölümlerini temizledikten sonra istekte bulunan bilgisayara gönderebilir. Proxy server, virüslü dosyaları otomatik olarak temizleyebilir. Ayrıca, ağda hiç kimsenin internete doğrudan erişimi olmadığı için bir virüsü veya zararlı bir programı yayma ihtimalini azaltır, [kötü amaçlı yazılımlara](http://ensarkarabudak.com/siber-guvenlik/kotu-amacli-yazilimlar-turleri/) karşı filtre uygulayarak güvenliği artırır.
Bir proxy server ağ içerisindeki kullanıcıların IP adreslerini gizleyerek tüm kullanıcıların tek bir adres üzerinden ağ dışına çıkmasını sağlamaktadır. Böylece, saldırıda bulunmak isteyen kullanıcılar iç ağdaki kullanıcıların IP adreslerini göremez.

Proxy server’lar firewall (proxy server kendi üzerinde firewall içerir),spam filtresi (spamların sunucuya ulaşmadan proxy server ile tespiti ve engellenmesi böylece posta sunucusunun yükünün azaltılması sağlanabilir), DNS server ve IP gizleme Olmak üzere 4 temel kullanım özelliğine sahiptir.
Bir proxy server çeşitli kullanım alanlarına sahiptir. Bunlardan bazıları;

İç ağdaki kullanıcıları dışarıdan gelecek saldırılara karşı korumak için kullanılır.

Kaynaklara erişim hızını artırmak için kullanılır. (Ağ içerisinden sürekli istekte bulunulan servisler, web sayfaları veya dökümanlar proxy server önbelleğine alınarak sonraki erişimler buradan sağlanır)

Ağ servisleri veya içerikler için erişim politikası uygulamak için kullanılır.Örneğin, ağ içerisinden bir siteye erişim engellenebilir.

İnternet servis sağlayıcı veya kurum tarafından yasaklınmış sitelere erişim için kullanılır.

İç ağdaki kullanıcıların ağ ve internet erişimlerini kayıt altına almak ve raporlamak için kullanılır.

Güvenlik denetimlerini artırmak için kullanılır.

Kötü amaçlı içeriğin tespiti için kullanılır.

Ağ üzerindeki virüslerin tespiti ve yayılmasını engellemek için kullanılır.

### Proxy Server Türleri

##### Anonymous (Anonim) Proxy

Anonymous proxy server’lar web server olarak da adlandırılır. Internet ve LAN’larda çoğunlukla kullanılan proxy server’dır. Çoğunlukla web gezintilerinde iç ağdaki kullanıcıların IP adreslerini gizleyerek tek bir 1P adresinden erişim sağlar. Kullanıcı proxy server arkasında kalır. Ancak, erişilen internet sitesine erişim bilgileri olarak proxy server ve kullanıcının bilgileri gönderilir. İlk bakışta sadece proxy server bilgileri görünse de detaylı inceleme ile kullanıcının bilgileri de görülebilir.

##### High Anonymity Proxy

Elite proxy server olarak da adlandırılır. Bu tip proxy server’da bir siteye erişim sağlayan kullanıcının 1P adresi dışındaki bilgileri (kullandığı tarayıcı, işletim sistemi gibi) erişilen siteye gönderilir. Kullanım sayısı çok azdır. Bu tip server’lar kötü amaçlar ile kullanılmaya başlandığı için kullanımında bazı kısıtlamalar getirilmiş, bazı ülkelerde kullanımı özel izine bağlanmış ve kullanan kişilerin bilgilerinin 5 yıl saklanma zorunluluğu getirilmiştir.

##### Transparent Proxy

Bu tür proxy server’lar kullanıcının taleplerini ilgili siteye iletirken kendisini gizleyerek kullanıcının bilgileri ile iletir. Karşı taraf isteğin proxy server’dan geldiğini anlayamaz. Özellikle belirli IP adresine sahip kullanıcıların erişimine izin verilen sistemlere erişim için kullanılır.