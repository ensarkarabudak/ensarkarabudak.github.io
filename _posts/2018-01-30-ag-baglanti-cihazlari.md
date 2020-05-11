---
layout: post
title: "Ağ Bağlantı Cihazları"
---

## Ağ Arayüz Kartı (MC-Network interface Card)

Ağ arayüz kartı donanımsal bir elemandır ve bağlı olduğu cihazı iigili ağa dahil etmek için kullanılır. Diğer bir ifadeyle ağ kablosunun takıldığı donanım birimidir.
Masaüstü bilgisayarlarda PC! yuvaya takılan bu kart günümüzde bir çok anakartta tümleşik olarak gelmektedir. Laptoplarda ise kablosuz olarak kullanılabileceği harici olarak PCMClA yuvaya da takılarak kullanılabilir. Günümüzde ağ arayüz kartı olarak çoğunlukla ethernet kartları kullanıldığı için NlC denildiğinde ilk akla gelen ethernet kartıdır. Dünya üzerindeki tüm ethernet kartlarını birbirinden ayırmak için üzerlerinde MAC (Media Access Contol) adı verilen bir adres barındırırlar ve her kartın MAC adresi birbirinden farklıdır. MAC 48 bitlik bir adrestir. Bu nedenle 248 adet MAC adresi yani ağ arayüz kartı tanımlamak mümkündür.

## HUB

Temel ağ cihazlarındaııdır. Yıldız topolojisindeki ağlarda merkezde bulunur ve ağdaki tüm cihazlar ethernet kart) iizerinden hub’a bağlıdır. Herhangi bir yönetime sahip olmayı sadece cihazları birbirine bağlar. Ağ üzerindeki iki cihaz arasında veri alış verişi gerçekleştiriieceği zaman gönderici cihaz veriyi hub’a gönderir ve hub ağdaki tüm cihazlara veriyi iletir, ,sadece hedef bilgisayar veriyi alır. Ağın tamamına veriyi dağıttığı için ağda fazla trafik oluşumuna neden olur. Sadece bit seviyesinde işlem yapmaktadır. Token ring topolojisinde merkezde MAU bulunur ve görevi hub’la aynıdır.

Hub kullanılan ağlarda çift burgulu kablo kullanılır. Eğer ağ genişletilmek isteniyorsa birden fazla hub birbirine koaksiyel, çift burgulu veya fiber optik kabloyla bağlanabilir. Ancak, hub kullanılarak ağ genişletmede en fazla 3 hub birbirine bağlanabilir.Hubları birbirine bağlarken kullanılabilecek birkaç yol vardır. Bunlar; o Hub üzerinde bulunan uplink portu ile bağlantı yapılırken çift burgulu düz kablo kullanılır ve kablonun bir ucu hub’da herhangi porta diğer ucu diğer hub’ta uplink portuna takılır.
İki hub birbirine bağlanırken çift burgulu çapraz kablo kullanarak hublar üzerindeki herhangi portlar kullanılabilir.Eğer kullanılan ağ token ring ise ve birden fazla MAU birbirine bağlanacaksa MAU’lar üzerinde bulunan RI (Ring In) ve RO [Ring Out) portları kullanılır.

Hublar Aktif ve Pasif olmak üzere 2 gruba ayrılır. Aktif hub, gelen sinyalleri güçlendirerek iletir. Yani, çift burgulu kablolarda bulunan 100 metre sınırını aşmak için kullanılabilir. Pasif hub ise gelen sinyali güçlendirmeden üzerinde bulunan portlarda bağlı cihazlara iletir. Bu nedenle kablo mesafesini artırmak için kullanılamazlar.

## Switch (Anahtar Cihazı)

Switch’ler temel görev olarak hub’larla aynı olmakla beraber çalışma şekli farklıdır.,Veri iletimi anahtarlamalı olarak gerçekleştirilir. Yani veriyi gönderen cihazla alan cihaz arasında yol kurularak iletim gerçekleştirilir. Bundan dolayı performansları hub’lardan çok daha yüksektir. Hub’lar veriyi tüın ağa yararken switch’ler üzerinde bulundurdukları MAC adres tablosu sayesinde her bir portta bağlı cihazın MAC adresini bilir ve veriyi ilgili porta yönlendirir.
Switch’ler yıldız topolojisinde merkezde kullanılabildiği gibi paket anahtarlamalı farklı ağları da birbirine bağlamak için kullanılabilir.
Switch kullanılan bir ağda iki cihaz arasında veri iletimi yapılırken, gönderici veriyi swtich’e iletir. Gelen veri içerisinde hedef cihazın MAC adresi switch tarafından kontrol edilerek hedef MAC adresine sahip cihazı switch üzerinde bağlı olduğu port tespit edilir ve veri sadece ilgili porta yönlendirilir. Eğer switch üzerinde hedef MAC adresinin bağlı olduğu port bulunamazsa veri tüm portlara gönderilir.
Ayrıca gelen veri için gönderen ve alıcının MAC adresleri aynı ise veri silinir.
Hub’larda olduğu gibi switch’lerde birbirine bağlanarak ağ genişletilebilir.Güncel switchler üzerinde çoğunlukla hublarda olduğu gibi uplink portu yoktur. Ya da 24 portlu ise 25 ve 26 nolu portlar uplink için ayrılmış olabilir. İki switch birbirine bağlanırken düz ve çapraz kablo kullanılabilir. Çünkü günümüz switchleri kullanılan kablo bağlantı tipini otomatik belirleyebilmektedir.
Switchler veri iletim türüne yani kullanılan paket anahtarlamaya göre iki moda sahiptir. Bunlar;

**Cut Through Mod**: iletilecek veri switche geldiğinde ilgili porta yönlendirilerek veri iletimi gerçekleştirilir. Bu yöntemde sadece hedef adres saklandığı için iletim zamanı daha kısadır ama hata denetimi gerçekleştirmez. Yani hatalı veri paketleri de ağ üzerinde iletilmeye çalışılır.

**Store and Forward Mod:** Bu tür switchlerde iletilecek veri switch üzerinde buffer’a atılarak hata kontrolü gerçekleştirilir. Eğer veri hata içermiyorsa hedef port tespit edilerek veri iletimi gerçekleştirilir. Bu yöntemde verinin tamamının switche yüklenmesi gerektiği için gecikme oluşacaktır.

Günümüzde üretilen switchler büyük çoğunlukla **100Mbps** hızlarında üretilmekte olup, üzerinde 1 veya 2 adet Gigabit portu bulunan veya tüm portları Gigabit olan switchlerde bulunmaktadır. Ancak, tüm portları Gigabit olan switchlerin fiyatları * doğal olarak daha yüksektir. Ayrıca switchler ilerleyen bölümlerde bahsedeceğimiz OSI katmanında bulunduğu yere göre Z’ye ayrılır. Bunlar; Katman 2 switchler ve Katman 3 switchlerdir. Buraya kadar bahsettiğimiz switchler Katman 2 switclıler olup OSI katman 2 (Veri Bağı Katmanı)’de yer almaktadır. Katman 3 switchler yönetilebilir switchler olarak da geçmektedir ve OSl katman 3 (Ağ Katmani)’de yer alır.

**Katman 3 Switchler (Yönetilebilir Switch):** Bu tür switchler katman 2 yani yönetilemez swtichlerin tüm özelliklerini barındırır ve üzerlerinde barındırdıkları yazılımlar sayesinde ağ üzerindeki trafik kontrol edilebilir.Ayrıca, ağdaki cihazların izlenmesi için Simple Network Management Protocol (SNMP ağlar üzerindeki birimleri denetlemek amacıyla tasarlanmıştır. Cihaz üzerindeki sıcaklıktan, cihaza bağlı kullanıcılara, internet bağlantı hızından sistem çalışma süresine kadar çeşitli bilgiler SNMP’de içinde tutulurlar) gibi protokoller kullanılabilir, VLAN (LAN üzerindeki ağ kullanıcılarının ve kaynakların mantıksal olarak gruplandırılması ve switch üzerinde port’lara atanması) oluşturulabilir, portlar üzerinde güvenlik protokolleri uygulanabilir, istenilen port kapatıp açılabilir. Kısaca yönetilebilir switchler switch ve router’ın ortak özelliklerine sahiptir.

## Repeater(Tekrarlayıcı)

Bir ağ oluşturulurken en büyük sorunlardan birisi kullanılacak kablonun maksimum mesafesidir. Örneğin, UTP kablolar maksimum 100 metre kullanılabilir.Eğer mesafenin daha fazla olması isteniyorsa sinyal güçlendirilerek tekrar iletilmesi gerekir.

Repeater, alınan sinyali bit seviyesinde yenileyerek yani güçlendirerek ve zamanlayarak tekrar iletilmesini sağlar. Aksi durumda maksimum mesafeden _sonra sinyal zayıflayacağı için veri iletimi gerçekleştirilemez. Sinyali güçlendirmenin yanı sıra bozulan sinyallerin iyileştirilmesini sağlar.

Repeater, telefon, telgraf, optik haberleşme ve mikrodalga gibi birçok alanda kullanılmaktadır ve hepsinde temel görevi aynıdır. Çoğunlukla kablosuz ortamlarda kullanılır. Çünkü kablolu ortamlarda kullanılan switch, hub ve router gibi cihazlar aynı zamanda tekrarlayıcı olarak çalışmaktadır.

## Bridge (Köprü)

Bridge, aynı protokolü kullanan iki veya daha fazla ağı birbirine bağlamak için kullanılır Çoğunlukla ethernet ve token ring tabanlı ağları birbirine bağlamak için kullanılır. İki ağ arasındaki veri iletimini gerçekleştirirken verinin hedef adresi birleştirilen ağlardaki bir hedefe karşılık geliyorsa verinin diğer ağa geçmesine izin verir, aksi durumda ise verinin geçişini engeller. Eğer veri iletimi birleştirilen ağların kendi içerisinde gerçekleşiyorsa verinin sadece ilgili ağ içerisinde kalmasını sağlar. Bu işlem yapılırken NlC’ler üzerinde bulunan MAC adresleri kullanılır ve haberleşen cihazların kendi içerisinde mi yoksa diğer ağ da mı olduğuna karar verir.

Bridge ile birbirine bağlanacak ağlar farklı topolojide olmak zorunda değildir. Yani 2 ethernet ağı da bridge ile birleştirilebilir. İlk akla gelen soru switch’de aynı işlemi yapıyor bridge kullanmanın avantajı nedir? Bridge kullanıldığında veri iletimi aynı ağda gerçekleştiriliyorsa verinin diğer ağ geçişine izin verilmez.
Bridge, bir ağ donanımı olabileceği gibi bir bilgisayar ve yüklü yazlım veya işletim sistemi de bu görevi gerçekleştirebilir.

## Router (Yönlendirici)

LAN-LAN, LAN -WAN, WAN-WAN gibi ağlar arası haberleşme için kullanılır. Ağlar arası veri transferini sağlar. Router’ın işlemcisi, eprom’u ve işletim sistemi (IOS -Internal Operating System) vardır. Bu sayede router üzerinde programlama işlemi yapılabilmektedir. Veri iletimi esnasında verinin yönlendirilmesi için gerekli kararları verme yeteneğine sahiptir. İletim için birden fazla yol arasından en iyi yolu seçer.

Router’ın temel amacı gelen paketleri inceleyerek hedefine ulaşması için en uygun yönlendirmeyi gerçekleştirir. İletim esnasında sadece ağ adresi bilinen verilerin iletimine izin vererek ağ trafiğini azaltır.

Router dinamik ve statik olmak üzere iki gruba ayrılır. Dinamik router, iletilecek veri için kullanılacak en iyi yolu kendisi belirler. Statik routerda kullanılacak yol elle belirlenir ve hep belirlenen yol kullanılır. Statik router’lar dinamik router’lardan daha güvenlidir.

## Gateway(Ağ Geçidi)

Farklı tipteki ağları birbirine bağlamak için kullanılır. Bu sayede IP-IPX veya ISDNX25 gibi farklı protokolleri kullanan ağlar haberleşebilir. Bu cihaz bridge, switch veya router olabileceği gibi yazılımsal olarak da gerçekleştirilebilir. Örneğin, windows ağ yapılandırılmasında girilen ağ geçidi numarası ağdaki yönlendiriciyi kastetmektedir.

## Transciever (Dönüştürücü)

Farklı fiziksel yapıya sahip kabloların birbirine bağlanması için kullanılır. Örneğin, biri UTP diğeri fiber optik olan kabloların birbirine bağlanması için kullanılabilir. Dönüştürücülerin çeşitli varyasyonları vardır. Örneğin, fiberden R]4S’e. AUI’dan Rl45’e, RI45’den BNC’ye gibi.

## Access Point (Erişim Noktası)

Access Point kablolu ağ ortamının kablosuza dönüştürülmesi için veya kablosuz ağ ortamının etki alanın genişletilmesi için kullanılır. Örneğin, kablosuz modeme sahip olmayan bir kullanıcı modemin veya modeme bağlı switcihin herhangi bir portuna access point bağlayarak kablosuz internet de kullanabilir. Başka bir örnek ise kablosuz ağın etki alanın yeterli olmadığı durumlarda access point kullanarak mevcut kablosuz ağın sinyallerini güçlendirip etki alanın genisletebilir, Bu tür durumlarda access pointin herhangi kablo bağlantısı yapmaya gerek yoktur.

## Modem

Modemler, telefon hatları yardımıyla bilgisayarların inter sağlayan cihazlardır. Modülatör ve Demodülatör kelimelerini birleşiminden oluşur. Bilgisayardan aldıkları sayısal verileri dönüştürerek telefon hatları yardımıyla iletilmesini sağlar. Modemler genel olarak 4 grupta incelenebilirler.
Analog modemler, sayısal verileri analog sinyallere veya analog sinyalleri sayısal verilere çevirirî Kişisel bilgisayarların internet erişimi için kullanılır.
Sayısal modemler, herhangi bir sayısal analog dönüşümü yapılmaz Veri sayısal olarak iletilir.