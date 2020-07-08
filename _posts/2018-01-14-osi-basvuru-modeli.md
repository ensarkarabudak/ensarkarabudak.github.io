---
layout: post
title: "OSI Modeli,OSI Katmanları Nelerdir?"
tags:
  - ağ
---

İki bilgisayar arasındaki iletişimi biçimsel olarak tanımlayan ilk kuruluşlardan birisi ISO **(International Organization for Standardization)**‘dur. ISO uluslararası veri iletişimi standartları geliştiren bir kuruluştur. ISO 1970’lerde OSI (Open Systems Interconnection) mimarisini geliştirmiştir. OSI ağ sistemleri için bir kılavuz niteliğindedir. OSI öncesinde donanım üreticilerinin kendilerine özgü ağları bulunmakta ve farklı üreticilere ait donanımlar aynı ağda çalışmamaktadır. OSI ile birlikte farklı üreticilere ait donanımlar arası uyumsuzluk ortadan kalkmış ve bilgisayarlar arası iletişim ortak bir standarda oturtulmuştur.

OSI **yedi katmana** ayrılmıştır ve iletişim esnasında kullanılan protokoller ve donanımlar bu katmanlarda yer alır. İki bilgisayar arasında veri iletimi gerçekleştirileceği zaman veriyi gönderen için iletim en üst katmandan başlar alt katmanlara doğru devam eder. Veri alan için ise durum tersidir. Yani gelen veri en alt katmandan başlar ve üste doğru devam eder. En üst katman kullanıcıya daha yakın olup uygulamaları içerirken alt katmanlara doğru veri makine diline ve en son bit seviyesine kadar düşer. OSI modeli sayesinde bir donanım veya protokolün ağ içerisindeki görevi daha kolay açıklanabilir.

## Fiziksel(Physical) Katman

Bu katman verinin kablolar üzerinden **iletiminden** sorumludur ve verinin Karim ilgilenmez. Verinin elektrik, ışık veya radyo sinyallerine çevrim şekli ve aktarım tanımlar. Veriyi gönderen taraf 1 ve O’lardan oluşan veriyi iletim şekline göre (IŞIK radyo veya elektrik) çevrimini, alıcı taraf ise gelen sinyalleri 1 ve O’lara çevrilir.Ağ cihazlarından HUB’lar fiziksel katmanda tanımlıdır. Fiziksel katman iletişim türleri RS-232, iOBase-T, IOOBase-TX, lSDN, DSL vb.

## Veri Bağı(Data Link) Katmanı

Fiziksel katmana erişim ile ilgili kuralları düzenler. Bu katmanda gerçekleştirilen işlemlerin büyük bölümü ağ arayüz kartı içerisinde gerçekleştirilir.
Bu katman ağdaki bilgisayarların tanımlanması, hattın hangi bilgisayar tarafından kullanıldığının belirlenmesi ve fiziksel katmandan gelen verinin hata denetimı görevini yerine getirir. Eğer veri ağ katmanından geliyorsa ağ katmanından aldığı verilere **hata kontrol** bitlerini ekleyerek fiziksel katmana aktarmayı gerçekleştirir. İletilen verinin doğru mu yoksa hatalı mı iletildiğini eklediği hata bitleri ile kontrol eder ve hatalı iletilmişse tekrar gönderir.

Veri bağı katmanı LLC (Logical Link Control) ve MAC (Media Access Control) alt katmanları olmak üzere iki bölümden oluşur. MAC alt katmanı, ağ katmanından gelen veriye hata bitlerini, alıcı ve gonderlcl MAC adreslerini ekleyerek fizıksel katmana aktarır. MAC alt katmanı veriyi alan tarafta da aynı işlemlerin tersini yapıp veriyi LLC alt katıııaıııııa aktarır. LLC .ılt katmanı. ağ katmanına geçiş gorevi görür. LLC ait katmanı alıcı-gönderici bilgisayarlarda aynı protokollerin kullanılmasını ve bozuk paketlerin tekrar gönderilmesini sağlar. Ayrıca, akış kontrolü ile aşırı yüklenmeyi önler. Bu katmanda Ethernet. Token Ring, FDDl, ATM,Frame Relay ve PPP iletişim kuralları bulunmaktadır.Ağ cihazlarından Switch ve Bridge veri bağı katmanında tanımlıdır.

## Ağ (Network) Katmanı

Bu katman gelen veri paketlerinin ağ adreslerini kullanarak uygun ağlara yönlendirilmesini sağlar. Ayrıca. ağdaki cihazların adresleme işlemlerini gerçekleştirir. **Router** ve yönetilebilir switch bu katmanda yer alır. Ayrıca, veri paketi farklı bir ağa yönlendirilecekse router’ların kullanacağı bilgi bu katmanda eklenir.
Temel görevi, Taşıma katmanından gelen **istekleri cevaplandırmak** ve bu hizmetleri Veri Bağı katmanına iletmektir.IP, ARP(IP adresinden fiziksel adrese dönüşüm gerçekleştirir),ICMP (Sistemler arası kontrol mesajı için kullanılır],IPsec (IP protokolünün güvenlik ihtiyaçlarını gidermek için geliştirilmiştir),IPX (Netware sistemlerde adresleme için kullanılır) ve AppleTalk (Apple tarafından geliştirilen ve MAC üzerinde kullanılan adresleme protokolüdür) bu katmanda kullanılan protokollerdir.

## Taşıma(Transport) Katmanı

Bu katman 5-7 ve 1-3 katmanları arasında bağlantıyı sağlar. Üst katmandan gelen **veriyi bölümlere** ayırarak alt katmanlara, alt katmandan aldığı bölümleri de birleştirerek üst katmana gönderir. Ayrıca akış kontrolü ile verinin alıcısına ulaşıp ulaşmadığını ve bölümlere ayrılan verinin aynı sırada birleştirilmesini sağlar. Veri iletimini gerçekleştiren TCP, UDP, SPX, SCTP ve DCCP protokolleri bu katmanda yer alır.

## Oturum(Session) Katmanı

İletişim gerçekleştirilecek iki cihaz arasında oturumun kurulması, kontrolü ve sonlandınlmasını sağlar. Örneğin.İki bilgisayar arasında veri transfer; gerçekleştirilirken üçüncü bir bilgisayar bunlardan birisi ile iletişim kuram oturum katmanı bu iki iletişimi de organize etmek zorundadır. Ayrıca, ven iletim; esnasında sorun oluşursa bağlantının tekrar kurulmasını sağlar. Cihazlar arasındaki iletişim turu de (simplex, half-duplex, full-duplex) yine bu katmanda belirlenir.Örneğin. NetBlOS (ağa bağlı aygıtların birbiriyle haberleşmesini sağlayan bir API). SSL (internet üzerinde güvenli iletişim sağlayan bir yapıdır), SOCKS (isteme ve sunucu arasındaki paketlerin yönlendirilmesini sağlayan bir internet protokolü
protokolleri bu katmanda yer alır.

## Sunum(Presentation) Katmanı

Sunum katmanın temel görevi iletimi gerçekleştirilen verinin alıcı bilgisayar tarafından yani uygulama katmanı tarafından anlaşılabilir hale dönüştürülmesidir. Kısaca iletimi gerçekleştirilen veriyi bazı kurallara göre standartlaştırır. Ayrıca. bu katmanda veriyi sıkıştırma-açma. şifreleme-şifre çözme. Unicode-ASCII veya tersi dönüşüm işlemleri gerçekleştirilir.

Örneğin farklı işletim sistemleri içeren iki bilgisayar arasında veri transferi gerçekleştirilirken kodlamalar farklı olacaktır. A işletim sisteminde X verisi 8 bit iken diğerinde 16 bit olabilir. Sunum katmanı bu verinin her iki işletim sistemi tarafından aynı şekilde yorumlanmasını ve aynı sonucu üretmesini sağlar.

## Uygulama(Application) Katmanı

Kullanıcıya en yakın katman olup kullanıcı tarafından çalıştırılan tüm uygulamalar bu katmanda yer alır Uygulamalar ile ağ arasındaki ara birimdir. Dosya paylaşımı. e-mail veya veritabanı yönetimi gibi işlemlerin gerçekleştirildiği katmandır Uygulama katmanında HTTP. SMTP, POP. DHCP. FTP. Telnet, DNS gibi protokoller kullanılır. Örneğin. bir kullanıcı bir web sayfasını ziyaret etmek için tarayıcıyı açması uygulama katmanında gerçekleştirilir. Çünkü, HTTP uygulama katmanı protokoludür.