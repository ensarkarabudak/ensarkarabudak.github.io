---
layout: post
title: "Linux İşletim Sisteminde Root(kök kullanıcısı) Yönetimi"
---

Linux İşletim Sisteminde Root(kök kullanıcısı) Yönetimi

Linux, diğer UNIX tabanlı sistemler gibi, aynı anda birden fazla kişi tarafından kullanılmak üzere tasarlanmıştır. Çok kullanıcı özelliği, pek çok kişinin tek bir Linux sisteminde hesap oluşturmasına olanak tanımakla birlikte, kullanıcı verilerinin diğerlerine karşı güvende tutulmasını sağlar. Bir Linux sisteminin tüm kaynaklarını yönetmeye yetkili kişiye ise Linux sistem yöneticisi (system administrator) denir. Bu yazımızda Linux sistem yönetimi (system administration) kavramını ele alarak root yetkisi ve kullanımından bahsedeceğiz. Bu konudaki devam yazılarında yönetimsel komutlar, konfigürasyon dosyaları, log kayıtları ve donanım yapılandırması gibi konular ela alınacaktır.

Bir Linux sistemini tek başınıza kullansanız bile, sistem yönetimini bilgisayar kullanımından ayrı ele almalısınız. Çoğu yönetimsel işlemleri yapmak ya da sistem için kritik uygulamaları kurup çalıştırmak için, root oturumu açmanız ya da geçici olarak root yetkisi (genellikle sudo komutunu kullanarak) edinmeniz gerekir. Root iznine sahip olmayan normal kullanıcılar bir Linux sistemi için bazı yapılandırma ayarlarını değiştiremez hatta bazı durumlarda göremez bile. Özellikle, kayıtlı şifreler gibi güvenlik ayarları genel kullanıcılardan uzak tutulmaktadır.

## Root olmak

Bir Linux sistem yöneticisi, genellikle normal bir kullanıcı olarak oturum açtıktan sonra sadece ihtiyaç duyulduğunda yönetici ayrıcalıklarını kullanılmalıdır. Sistem yöneticisinin sitemi etkilemeyen işlemler için bile root yetkisini kullanması kazara sisteme zarar verebilecek sonuçlara neden olabilir.

Normal bir kullanıcı oturumunda iken root yetkisi (superuser) aşağıdaki yöntemlerle edinilebilir;

**su komutu:** root kullanıcısı olarak bir kabukta (shell) oturum açmak için kullanılır. Komut sonrası root parolası girilmelidir. Normal kullanıcılar için komut satırında görünen **“$”** simgesi “#” simgesine dönüşür. **“#”** simgesi ile birlikte verilen tüm komutlar root yetkisi ile verilmiş olur. Tekrar normal kullanıcı kabuğuna dönmek için çıkış yapmak gerekir (exit komutu). Aşağıdaki örnekte, whoami komutu ile sistemdeki hangi kullanıcı olduğumuzu sorgulayıp, root olduktan sonra sorgulamayı yineliyoruz.

**sudo komutu:** sudo ile normal bir kullanıcıya root yetkileri verilir. Ancak bu kullanıcı yalnızca bir komutu çalıştırmak için sudo komutunu kullanabilir. İstediği komutu sudo ile çalıştırdıktan sonra kullanıcı normal kabuğa geri döner (yani “$” simgesinde kalır, “#” simgesiyle işlem yapmaz”) ve normal kullanıcı olarak davranmaya devam eder. Ubuntu tabanlı dağıtımlarda genelde varsayılan olarak bir sistemdeki ilk kullanıcı hesabına sudo ayrıcalığı verilir. Fedora veya Red Hat ise varsayılan olarak bu ayrıcalığı vermez, kurulum esnasında bu ayrıcalığın seçilmesi gereki

**Grafiksel pencereler:** Uygulama menülerinden tıklayarak başlatılan çoğu grafiksel uygulama normal bir kullanıcı tarafından başlatılabilir. Ancak bazı araçlar root yetkisine ihtiyaç duyar ve çalıştırılmak istendiğinde bir grafik pencereden root parolası girilmesi istenir.

### root kullanıcısının görevleri

Yalnızca root kullanıcısı tarafından yapılabilecek görevler, sistemi bir bütün olarak veya sistemin güvenliğini etkileyen işlemlerdir. Bir sistem yöneticisinin yönetmesi beklenen bu işlemleri şöyle sıralayabiliriz;

**Dosya sistemi:** Linux dosya sistemi sistem kurulumunda kullanıcılar için otomatik olarak hazır hale getirilir. Ancak, kullanıcıların ekstra depolama alanı ihtiyacı ya da kendi HOME dizini haricindeki klasör değişiklikleri için yönetici haklarına gereksinim duyarlar. root kullanıcısı sistemdeki tüm klasörlere erişebilir (diğer kullanıcılara ait olanlara bile). İhtiyaç duyulan değişiklikleri yapar. Gerektiğinde güvenliği sağlamak için tüm dosya sisteminin yedeğini bile alır.
Yazılım yükleme: Zararlı yazılımların sisteme yüklenmesi sisteme ciddi zararlar verebileceğinden yazılım yüklemek için root yetkisine sahip olunması gerekir. Sistemi etkileyen bir özelliği yoksa yazılımları sistemdeki tüm kullanıcılar kullanılabilir. Genel kullanıcılar kendi dizinlerine bazı yazılımlar yükleyebilir ve sistem yazılımları hakkındaki bilgileri listeleyebilirler.
Kullanıcı hesapları: Yalnızca root kullanıcısı diğer kullanıcı hesaplarını ve grupları ekleyip kaldırabilir.

**Ağ arabirimleri:** Ağ arabirimlerini yapılandırma, bu arabirimleri başlatma ve durdurma işlemleri root kullanıcısı tarafından yapılır. Ancak günümüzde (mobilitenin artışıyla birlikte) pek çok dağıtım özellikle wi-fi ağının başlatılması ve durdurulması gibi işlemler için genel kullanıcılara da izin vermektedir. Bunun dışındaki optimizasyonlar için root yetkisine ihtiyaç duyulur.
Sunucular: Web sunucuları, dosya sunucuları, alan adı sunucuları, posta sunucuları ve daha birçok sunucuyu yapılandırmak, bu hizmetleri başlatıp durdurmak gibi işlemler root ayrıcalıkları gerektirir.
Güvenlik özellikleri: Güvenlik duvarları ve kullanıcı erişim listeleri gibi güvenlik özelliklerini ayarlama işlemleri genellikle root yetkisi ile yapılır. Ayrıca, hizmetlerin nasıl kullanıldığını izlemek ve sunucu kaynaklarının tükenmediğinden veya kötüye kullanılmadığından emin olma işi de root kullanıcısı tarafından yapılmalıdır.
Sistem yönetimine bazı grafik yönetim araçlarını kullanarak başlamak uygun olabilir.

### Grafiksel yönetim araçları

İlk Linux sistemlerinde, sistem yönetimi işlemleri komut satırından yapılırdı. Linux’un yaygınlaşması ile hem grafik hem de komut satırı arabirimleri ile yönetimsel görevler için ara yüzler sunulmaya başlandı.

İlk grafiksel sistem yönetim araçlarından bazıları Red Hat tarafından sunulmuştur. Red Hat’ın bu GUI (Graphical User Interface, Grafiksel Kullanıcı Arayüzü) araçlarını başlatan komutlar genellikle “system-config” ile başlar. Bir yazıcıyı yapılandırma veya tarih, saat ve saat dilimini ayarlama gibi temel yönetim görevlerini yerine getirmek için kullanabilirler.

**system-config araçlarını kullanma**

Çoğunlukla **Red Hat Enterprise Linux (RHEL)** sistemlerinde (ve bazıları Fedora’da) yer alan “system-config” araçları uygulama menülerinden ve komut satırında başlatılabilir. Bu araçların kullanımı için root yetkileri gerekir. Eğer normal bir kullanıcı olarak grafik arayüzden çalıştırdıysanız açılan pencereye, komut satırından başlattıysanız komut satırına root parolası girmeniz istenecektir.

RHEL ve bir kısmı Fedora’da yer alan bu araçlardan bazılarına aşağıda yer veriyoruz;

Domain Name System (system-config-bind) – Fedora
HTTP (system-config-httpd) – Fedora
NFS (system-config-nfs)- Fedora
Root Password (system-config-rootpassword) – Fedora
Samba NFS (system-config-samba) – Fedora
Services (system-config-services) – Fedora ve RHEL
Authentication (authconfig-gtk) – Fedora ve RHEL
Date & Time (system-config-date) – Fedora ve RHEL
Firewall (system-config-firewall) – Fedora ve RHEL
Language (system-config-language) – Fedora ve RHEL
Printing (system-config-printer) – Fedora ve RHEL
SELinux Management (policycoreutils-gui) – Fedora ve RHEL
Users & Groups (system-config-users) – Fedora ve RHEL
root kullanıcı hesabını kullanmak

Her Linux sisteminde en az bir yönetici hesabı (root hesabı) bulunur. Bunun dışında yönetici ayrıcalıkları atanmış bir veya birden çok normal kullanıcı (yani bir sisteme giriş adı -login name- olan) da bulunabilir. Bu yönetici ayrıcalıkları verilen kullanıcılar ise çoğu durumda Linux sistem yönetimi için root yetkilerini yukarıda anlattığımız şekillerde kullanır.

root kullanıcısı Linux sisteminin kontrolüne tamamen sahiptir. Bu kullanıcı tüm dosya ve sistem kaynaklarına erişebildiği gibi tüm uygulamaları çalıştırmaya da yetkilidir. Microsoft Windows sistemlerindeki “Administrator” kullanıcısı gibi düşünülebilir.

Çoğu Linux sistemi kurulurken (bazı sistemler hariç) bir **root** kullanıcı parolası atanması istenir. Bu parola hiçbir şekilde unutulmamalı ve korunmalıdır.

root kullanıcısı için tanımlanan home dizini diğer kullanıcılardan farklı olarak /root klasörüdür. Diğer kullanıcılara benzer olarak ise root kullanıcısına ait bazı bilgiler de /etc/passwd ve /etc/shadow dosyasında saklanır. Kullanıcı yönetimi konusundaki yazımızda bu dosyaların içeriğini ve özelliklerini anlatmıştık.

**root yetkisi** kullanarak komut satırında işlem yaparken (sudo ya da su komutu ile) dikkatli olunması gerekir. Zira yetkinin büyük olması sisteme daha büyük zararlar verilmesine neden olabilir. Bu nedenle yönetimsel bir işlem sonrası exit komutu ile root oturumunu terk etmek faydalı olabilir.

Ubuntu dağıtımlarında varsayılan olarak root kullanıcı hesabı ile ilişkilendirilen bir root parolası yoktur. Yani su komutunu vererek kalıcı bir şekilde root olamazsınız. Ancak yönetimsel işlemlerde sudo komutu kullanarak root yetkilerinizi kullanabilirsiniz. Ubuntu tarafından böyle bir **güvenlik önlemi** uygulanmaktadır.



**KAYNAK:https://teknopusula.com/linux-sistem-yonetimi-1-sistem-yonetimine-bakis-ve-root-hesabi-6828**