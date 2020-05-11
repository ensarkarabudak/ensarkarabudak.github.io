---
layout: post
title: "Linux’a Arduino Kurulumu"
---

Linux işletim sistemine **Arduino** bütünleşik geliştirme ortamını yani IDE kurulumu diğer işletim sistemlerine nazaran biraz daha kolay ya da **kolay** yolları mevcut diyebiliriz.Arduino’yu linux işletim sistemine kurmanın avantajı ise Arduino geliştiriciler Linux ortamında çalıştıkları için Arduino’ya gelen **güncellemeler** ve yenilikler ilk olarak Linux ortamında görülüyor.


Arduino kurulumunu ben **Linux Mint 18.1** üzerinden anlatacağım.Bu kurulum Ubuntu başta olmak üzere diğer Linux dağıtımlarının çoğunda da geçerli olup rahatlıkla uygulayabilirsiniz.
Linux’a Arduino Kurulumu için **2 yöntem** vardır.

##### **1.Yöntem**

Bu yöntem ile çok basit bir şekilde Arduino IDE’yi yükleyebilirsiniz.

İlk olarak ‘menü’ kısmına geliyoruz.

Yazılım yöneticisini açıyoruz.

![image-center]({{ '/images/LinuxArduino/Linuxa-Arduino-Kurulumu-.png' | absolute_url }}){: .align-center}


Arama yerine ‘Arduino’ yazıp kuruyoruz.

![image-center]({{ '/images/LinuxArduino/Linuxa-Arduino-Kurulumu2.png' | absolute_url }}){: .align-center}


Daha sonra uygulamayı açarak IDE’yi açabilirsiniz.

##### **2.Yöntem**

Bu yöntemde ise **uç birim(terminal)**den yapabilirsiniz.

İlk olarak Arduino sitesine giriyoruz ve şuanda güncel olan
Arduino IDE’sinin 1.8.1 sürümü indiriyoruz.

İndirdiğimiz dosyayı dışarıya çıkarıyoruz.

![image-center]({{ '/images/LinuxArduino/Linuxa-Arduino-Kurulumu4-.png' | absolute_url }}){: .align-center}


**Klasörün çıkarttığımız klasörde** sağa tıklayarak terminali açıyoruz.Daha sonra aşağıdaki kodu yazıyoruz.

```bash
sudo mv arduino-1.8.1 /opt
```

> Not:Burada eğer yeni sürüm çıktı ise sürümü değiştirmeniz gerekir.

Daha sonra aşağıdaki kodu sırayla yazıyoruz.

```bash
cd /opt
cd arduino-1.8.1
chmod +x install.sh
./install.sh
```

> Not:Yukarıdaki 4 satırlık kodu **ayrı ayrı** yazarak çalıştırınız.

Kodların terminalde görünümü ise şu şekilde olması gerekir:

![image-center]({{ '/images/LinuxArduino/Linuxa-Arduino-Kurulumu3.png' | absolute_url }}){: .align-center}

**Kurulum tamamlandı.**Menüden Arduino yazarak uygulamanızı açabilirsiniz.