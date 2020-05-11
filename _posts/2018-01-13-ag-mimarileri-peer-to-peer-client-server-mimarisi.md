---
layout: post
title: "Ağ Mimarileri,Peer-to-Peer ve Client-Server Mimarisi"
---

Ağ Mimarileri Ağ üzerindeki cihazların iletişim şekline göre ağlar **Peer-to-Peer** ve **Client-Serve**r olmak üzere iki gruba ayrılır.

## Peer-to-Peer (Eşler Arası) Mimari

Bu tür mimariye sahip ağlarda tüm bilgisayarlar aynı haklara ve yapıya sahiptir. Ağdaki tüm bilgisayarlar hem istemci hem de sunucu gibi görev yapabilir. Merkezi bir sunucuya ihtiyaç duyulmaksızın ağdaki tüm bilgisayarlar karşılıklı paylaşımlarda (dosya, yazıcı, internet vb.) bulunabilir.
Bu tür ağlar genellikle evlerde ve merkezi yönetim gerektirmeyen işyerlerinde kullanılır.

## Client-Server (İstemci-Sunucu) Mimarisi

Ağdaki her bilgisayarın rolü farklıdır. Bu roller client (istemci) ve server (sunucu) olabilir.Bu mimaride merkezde sunucu bilgisayar bulunur ve dosya/kaynakların kullanımını,kullanıcıların yetkilerini ayarlamakla sorumludur.Donanımsal olarak da istemci bilgisayardan çok üstün özelliklere sahiptir. İstemci bilgisayarların tümü sunucu bilgisayara bağlıdır ve sunucunun verdiği yetkiler doğrultusunda işlemler gerçekleştirebilir. Ayrıca, istemci bilgisayarlar sunucudan bağımsız da hareket edebilir ama sunucunun sunmadığı hiçbir dosya veya kaynağı kullanamaz. Günlük hayatta sürekli kullandığımız internet erişimi bir client-server modelidir. internet Explorer istemci olarak web sayfası isteklerinde bulunur. web server da istekte bulunulan web sayfasını istemciye gönderir.

Client-Server mimarisi server yerleşimi açısından **2-tier** (2 katmanlı) ve **3-tier** (3 katmanlı) olmak üzere ikiye ayrılır.

##### 2-tier

Bu modelde istemci doğrudan sunucu ile iletişime geçebilir. Mimari isminde de geçtiği gibi client ve server olmak üzere 2 katman söz konusudur. Bu model bazı güvenlik açıklarına ve performans sorunlarına neden olmaktadır. Internet Explorer ve Web Server bu mimaride çalışmaktadır. Burada güvenlik sorunlarının önüne geçmek için SSL (Secure Socket Layer) kullanılmaktadır. Örneğin. sunucu bir veritabanı sunucusu ise istemci doğrudan veritabanı» sunucusundan bilgileri alabilecektir.

##### 3-tier

Bu mimaride istemci ve sunucu arasında ara bir katman söz konusudur. Bu katman güvenliği sağlamak ve istemcilere haklar sunmak için kullanılır. Bu katman istemciden gelen tüm istekleri alır ve kimlik doğrulama yaptıktan sonra sunucuya iletir. istemcinin isteği sunucudan geri dönerken önce orta katmana sonra istemciye iletilir. istemci, uygulama ve sunucu olmak üzere 3 katman vardır.