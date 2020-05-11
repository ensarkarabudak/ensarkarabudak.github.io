---
layout: post
title: "Ağ Topolojileri"
tags:
  - ağ
---

# Halka(Ring) Topolojisi
Halka topolojisi IBM tarafından geliştirilmiştir ve ağın yerleşimi halka biçimdedir. Ağ üzerinde iletilen veri hedefine ulaşıncaya kadar ağ üzerindeki her cihazdan geçer. Çünkü ağdaki iki cihaz arasında sadece bir yol vardır. Bu topolojide ağ üzerindeki sinyalin zayıflaması en düşük düzeydedir çünkü sinyal uğradığı her cihazında güçlendirilerek bir sonraki cihaza aktarılır. Ağ üzerinde veri iletimi jeton (token -3 byte) yardımıyla yapılır. jeton ağ üzerinde sürekli dolanır ve veri gönderecek cihaz jeton boş ise veriyi jetona yükler ve hedef adresi ile birlikte ağa tekrar bırakır. Halka üzerindeki bir ağ cihazının arızalanması ağın çökmesine neden olur.

Bu topolojinin çalışma şekli halka gibi görünse de aslında yıldızı anımsatır. Ağ yapısı merkezde bulunan MAU(Multistation Access Unit) cihazı ile bu cihaza bağlı ağ cihazlarından oluşur.


### Halka(Ring) Topolojisi Avantajları ve Dezavantajları

## Avantajları

Jeton sayesinde her cihaz veri iletim konusunda eşittir.

Cihazlar arasındaki bağlantılar için sunucuya ihtiyaç yoktur.

Ağın büyütülmesi performansı çok az etkiler.

## Dezavantajları

Ağ cihazlarından birisinde oluşacak sorun tüm ağı etkiler.

Ağ arayüz kartları ve MAU Ethernet ve switch’den daha pahalıdır.

Ağa cihaz ekleme, değiştirme veya çıkartma tüm ağı etkiler.


# Bus(Ortak Yol) Topolojisi

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


# Star(Yıldız) Topolojisi

Günümüzde en çok kullanılan ağ topolojisidir. Ağ üzerindeki her cihaz merkezde bulunan switch veya huba bağlıdır. Ağ üzerindeki verinin dolaşımı merkezde bulunan hub/switch ile gerçekleştirilir. Bir cihazdan diğerine gönderilen bilgi ilk olarak hub/swtich’e gelir ve buradan hedefe yönlendirilir.Bus topolojisine göre daha yüksek performans sunar. Hub veya switch’de oluşacak bir problem ağın tamamını etkiler ama ağ cihazlarında oluşan problem sadece o cihazı etkiler. Yıldız topolojisinde çift burgulu kablolar kullanılır. Ağ cihazlarının merkez cihaza uzaklığı maksimum 100 metredir. Ağdaki herhangi bir cihazın soruııu hub,/switch üzerindeki ışıklardan kolaylıkla anlaşılabilir.
Ağa bağlanan bir cihazın hub/switch üzerinde ilgili port ışığının yanması gerekmektedir.

### Yıldız(Star) Topolojisi Avantajları ve Dezavantajları

## Avantajları

Ağı genişletmek için yeni cihaz eklemek kolaydır.

Ağın yönetimi ve ağdaki hata tespiti kolaydır.

Herhangi bir cihazda oluşacak hata sadece o cihazı etkiler.

## Dezavantajları

Kullanılacak kablo miktarı fazladır.

Hub veya switch’de oluşabilecek sorun tüm ağı etkiler.