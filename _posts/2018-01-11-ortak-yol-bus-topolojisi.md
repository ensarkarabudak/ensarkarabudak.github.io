---
layout: post
title: "Ortak Yol (Bus) Topolojisi"
---

Bus topolojisinde iletişim tek bir kablo üzerinde gerçekleştirilir ve ağ cihazları bu kablo üzerine bağlanır. Bu tek kabloya segment (bölüm), backbone (omurga) veya trunk denilebilir. Ağda gönderilen veri hedefe ulaşana kadar veya sonlandırıcıya gelen kadar hat üzerinde devam eder ve tüm ağ cihazlarına uğrar. Ağın bant genişliği ağdaki cihazlar tarafından paylaşılır. Temel olarak bu topolojide koaksiyel kablo kullanılır. Ağ performansı en düşük olan topolojilerdendir. İnce koaksiyel kablo kullanıldığında maksimum 185 metre, kalın koaksiyel kullanıldığında maksimum mesafe 500 metredir. Maksimum 30 ağ cihazı kullanılabilir.

Bu topolojide ağa bağlı her cihaz ağ üzerindeki her işlemi ve veri iletimi dinler ve kendisine ait iletim söz konusu işe verir alır. Ağ üzerindeki herhangi bir aygıt veri paketi göndermeden önce hattın başkaları tarafından kullanılmadığından emin olur. Eğer ağa aynı anda iki farklı cihaz veri paketi gönderir ise çakışma meydana gelir ve Öncelik sırası cihazlar arasında kararlaştırılır.



### Ortak Yol(Bus) Topolojisi Avantajları ve Dezavantajları

## Avantajları

Kurulumu ve ağın genişletilmesi kolaydır.

Yüksek hız gerektirmeyen ağlar için hızlı bir şekilde kurulabilir.

Düşük maliyetlidir.

Kullanılan kablo miktarı daha azdır.

Merkezde switch/hub gibi bir cihaza ihtiyaç duymaması.

## Dezavantajları

Ana hat için kullanılacak kablo uzunluğu kolaydır ve bağlanabilecek ağ cihazı sayısı sınırlıdır.

Ana kablo üzerinde oluşabilecek bir hasar ağın tümünü etkiler ve çalışmaz hale getirir.

Sorun tespiti ve sorunun giderilmesi zordur.

Diğer topolojilerden daha yavaştır.

Ağa yeni cihaz ekleme veri yoğunluğunu artırır ve performans düşer.

Kablo sonlarında sonlandırıcı kullanılmalıdır.