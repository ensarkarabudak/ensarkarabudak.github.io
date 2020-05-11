---
layout: post
title: "DDoS nedir?,DDoS saldırısı nedir?"
---

DDoS nedir?,DDoS saldırısı nedir?,DDoS saldırısı nasıl yapılır? sorularını yanıtlamaya çalışacağım.DDos ve Dos nedirden önce **DNS(Domain Name Server)** kavramını bilmemiz gerekir.

DoS (Denial of Service, Hizmet Engelleme) saldırısının ne olduğunu öğrenelim.

#### DoS nedir?

Bir internet sitesine ulaşmak için bilgisayarınızla bir sunucuya bağlandığınızı
varsayalım. Sizin bilgisayarınız (istemci, **client**) sunucuya (**server**) bazı bilgiler sorarak karşılığında cevaplar alır.Bir nevi sunucu size hizmet verir. Her sunucunun belirli bir işlem yapma kapasitesi vardır.

Eğer sunucuya kapasitesinin üzerinde sorgu gönderirseniz tüm işlemler için **cevap veremez** ve hizmet veremez duruma düşer. İşte bu mantıkla yapılan sahte sorgular nedeniyle bir sunucunun hizmet sunmasını engellemeye **DoS saldırısı** denir.

#### DDoS saldırısı nedir?

DDoS saldırılarında aynı mantıkla sunucuların hizmet sunma kapasiteleri aşılmaya çalışılır.Ancak burada sorgu gönderen tek bir bağlantı ve **istemci** yerine yüzlerce hatta binlerce istemcinin sahte sorgular göndermesi söz konusudur. Binlerce istemciden aynı anda gelen milyonlarca sorgunun bir sunucuyu hizmet sunamaz hale getirmesi kaçınılmazdır.

##### DNS sunucularına yapılan DDoS saldırıları neden benim trafiğimi yavaşlatır?

DNS sunucularına sistemler üzerinden gönderilen sorgular DDoS saldırılarında aynı anda milyonları bulabilir.Bu şekilde sunucu her bir sorguya cevap vermez ve bazı sorguları engellemek zorunda kalır.
Hatta sunucu kapanabilir. Bu sahte IP sorgulamaları arasında elbette normal kullanıcıların sorgulamaları
da cevap bulamaz. Böylelikle normal kullanıcılar da istedikleri internet sitesine ulaşamaz ya da çok yavaş
bir bağlantı ile ulaşabilirler.