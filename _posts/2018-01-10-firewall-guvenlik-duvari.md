---
layout: post
title: "Firewall (Güvenlik Duvarı)"
---

Ağ üzerinde iletilen veri paketlerini **denetleyerek** istenmeyen trafiği veya erişimleri engellemek ve yerel ağ ile dış ağ arasında güvenliği sağlamak için kullanılır.**Firewal**l bir yazılım olabileceği gibi donanımsal bir cihaz da olabilir, Yazılımsal firewallar çoğunlukla ev kullanıcıları içindir. Donanımsal firewall ise genellikle **ağ sistemlerini koruma**k içindir.İyi konfigüre edilmiş bir firewall ile ağdaki istenmeyen tüm erişimler engellenebilir hatta ağdaki bilgisayarlar sadece yazı yazmak için kullanılabilir hale getirilebilir.

Firewall sadece **dış saldırılara** karşı sistemi korumaz, aynı zamanda performans arttırıcı ve izin politikası uygulayıcı amaçlar için de kullanılabilir.

Yeni nesil firewall’lar sadece erişim koruması sağlamayarak anti-virüs, anti-spam, lDS (lnstrusion Detection System Saldırı Tespit Sistemi), **VPN (Virtual Private Network Sanal Özel Ağ)** ve router gibi özelliklerde içerebilir. Bu tür cihazlar UTM (Unified Threat Management Birleştirilmiş Tehdit Yönetimi) cihazlar olarak adlandırılır.

## Firewall üzerinde sağlanan bazı ek servisler

### NAT (Network Address Translation)

LAN içerisindeki cihazların IP adreslerinin gizlenerek tek bir lP adresi ile dış ağa örneğin internete çıkış sağlar. Böylece dış dünyadaki kullanıcılar yerel ağdaki topoloji yapısını ve IP bilgisini göremezler.

### Paket Filtreleme

Ağ içerisine girecek olan her IP paketi firewall üzerinden geçerek eğer uygunsa ağ içerisine alınır. Filtreleme yapılırken [P paketi içerisindeki adreslere ve portlara bakılır. Örneğin, 123 nolu port üzerinden ağa girişe izin verilen paket 124 nolu port ile gelirse ağa girişine izin verilmez. Firewall üzerinde standart erişimler ve programlar için kullanılan port numaraları varsayılan olarak aktif durumdadır. Eğer bu portlar kapatılmak isteniyorsa veya
yeni portlara geçiş izni verilmek isteniyorsa firewall üzerinde ayarlama yapılmalıdır.

### Kaynak ve Hedef Adres Filtreleme

Ağ içerisinden dışarı çıkışların veya dış ağdan iç ağa gelen isteklerin adreslerine göre filtreleme sağlar. Örneğin, ağ içerisinden bir web sitesine erişim hedef adres filtreleme ile engellenebilir.
Ayrıca sürekli olarak belirli IP adreslerinden gelen saldırılar kaynak adres filtrelemesinde saldırı IP adresi belirtilerek engellenebilir.

### Dinamik Paket Filtreleme

Dinamik filtreleme paket filtrelemenin özelliği ile birlikte iletişim için kurulan oturumun takibini de gerçekleştirir. Bu filtreleme **Stateful inspection** ismiyle anılmaktadır.Stateful Inspection Firewall, iletilen veriyi kaynağından hedefine kadar takip eder ve veri paketi içerisinde daha önce zararlı olarak tanıtılmış koda rastlarsa verinin iletimine izin vermez.

### DMZ (De-Militarize Zone Açık Bölge)

DMZ, firewall tarafından en korunan bölgedir. LAN içerisindeki dışarıdan erişime açık sunucu ve bilgiler DMZ alanı içerisine yerleştirilerek dışarıdan erişim sağlayan tüm kullanıcılar buradaki bilgileri kullanabilir. DMZ oluşturmak için firewall üzerinde 3 adet ağ kartı bulunmalıdır. Bir kart iç network için, ikincisi internet için ve son kart da DMZ için kullanılacaktır.

### Proxy Firewall

Proxy(vekil) yapısında bir istemcinin isteği önce proxy’ye gönderilir ve isteği proxy gerçekleştirir. Proxy’nin bir diğer özelliği istekte bulunulan bilgi proxy’nin önbelleğinde var ise buradan isteğe cevap verilir eğer yoksa bu durumda kaynaktan istek gerçekleştirilir. Böylece, proxy firewall iletilen paketlerin içeriğini kontrol ederek istenmeyen komutlar ve içerik filtrelenebilir.

### Anti-virüs

Anti-virüs içeren firewall ağ üzerindeki virüslerin taranması ve temizlenmesi ve ağda yayılmasını engellemek için kullanılır.

### VPN

Kuruluş içerisindeki ağlara internet üzerinden şifreli ve güvenli bir şekilde erişim sağlamak ve ağın bir parçasıymış gibi çalışmak için oluşturulan sanal bir ağdır. Aynı işlem kiralık hatlarla da yapılabilir ama VPN düşük maliyetli ve yapılandırması kolaydır. VPN sanal olduğu için aynı anda birden fazla VPN
kullanıcısı ağı kullanabilir. VPN üzerindeki trafik internet üzerinden sağlandığı için güvenlik amacıyla şifreleme, veri doğrulama, yetkilendirme gibi güvenlik önlemeleri alınabilir.

### IDS

Ağ üzerindeki veya dışarıdan iç ağa yapılacak erişimlerde trafiği sürekli olarak izleyen ve şüpheli paketlerin iletimini engelleyen sistemlerdir.

### ICF (Internet Connection Firewall)

ICF ağa ve ağdaki bir cihaza dışardan erişim isteklerinin tümünü kayıt altına alarak saldırılara karşı sistemi korur.