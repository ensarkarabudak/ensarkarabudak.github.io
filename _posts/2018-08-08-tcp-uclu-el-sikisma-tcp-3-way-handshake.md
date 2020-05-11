---
layout: post
title: "TCP Üçlü El Sıkışma – TCP 3 Way Handshake"
tags:
  - ağ
---

İstemci-sunucu arasında bir veri akışının sağlanması için Üçlü El Sıkışma(3 Way Handshake) dediğimiz olayın gerçekleşmesi lazım.TCP/IP protokolü paketlerin doğru sırayla istenilen hedefe götüren bir ve ilk bağlantıyı sağlayan protokoldür.


![image-center]({{ '/images/3WayShake/TCP-Üçlü-El-Sıkışma-TCP-3-Way-Handshake.gif' | absolute_url }}){: .align-center}


#### Üçlü El Sıkışma(3 Way Handshake) Nedir?

Örneğin bir A bilgisayarı B bilgisayarına bir veri aktarmak istesin.A bilgisayarı istemci(client),B bilgisayarı sunucu(server) olsun.A bilgisayarından B bilgisayarına bir bağlantı kurmak için işletim sisteminin oluşturduğu rastgele bir sequence numarası ile **SYN**chronize mesajı yollanır.Bu yollanan bit “1” olarak ayarlanmıştır.

Ardından B bilgisayarından istemciye **SYN(Synchronize)** ve **ACK(Acknowledgement)**bayraklarını **“1”** olarak ayarlar ve A bilgisayarının gönderdiği SYN yani sıra numarasını bir artırıp **ACK numarası(Acknowledgement Number)** olarak ayarlayıp bu mesajı A bilgisayarına iletilir.Böylelikle A bilgisayarı sırayı doğru yapar hem de A bilgisayarının bir sonraki paket sıra numarası belirlenmiş olur.
Ayrıca B bilgisayarı da kendi işletim sistemi tarafından rastgele bir ACK numarası belirtilmiş olur ACK ve SYN paketini yollar.

Son olarak A bilgisayarı B bilgisayarının gönderdiği paketi alır sonraki paketi hazırlar ve ACK bayrağını **“1”** olarak ayarlar.B bilgisayarının gönderdiği sıra numarasını 1 arttırarak B bilgisayarına göndereceği paketin ACK numarası(Acknowledgement Number) olarak ayarlar.Artık SYN bayrağını değiştirmeye gerek yoktur.Çünkü bağlantı sağlanmış oldu **SYN ve ACK** paketini yollar.Bu sisteme **Üçlü El Sıkışma(TCP 3 Way Handshake)** denir.