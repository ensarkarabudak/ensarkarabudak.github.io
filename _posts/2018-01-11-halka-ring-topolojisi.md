---
layout: post
title: "Halka(Ring) Topolojisi"
---

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