---
layout: post
title: "HTTP Durum Kodları ve Anlamları"
tags:
  - http
---

Http durum kodları ve anlamlarına bakmadan önce şunu açıklayalım:HTTP durumu(Http Status) nedir?

İstemci(Client) HTTP kullanarak bir sunucuya istek atar.Bu istek doğrultusunda sunucundan ilk olarak bir yanıt alır biz buna HTTP durum kodu (HTTP Status Code) diyoruz. Bu komutları internet tarayıcınızda görebilirsiniz. En çok rastladığımız **HTTP Durum Kodları**:200, 301, 302, 404 ,500 ve 503’dür. Bu komutlar sayesinde Http server durumlarının sunucudan istemciye gelen mesajlarla hata,bilgi ve yönlendirme gibi bilgiler vermektedir.



### 1xx: Bilgi

| 101  | Continue             | Devam                 | İsteğin başarılı olduğunu belirtilir.                        |
| ---- | -------------------- | --------------------- | ------------------------------------------------------------ |
| 101  | Switching Protocols  | Anahtarlama Protokolü | İstemcinin protokol değiştirme isteğine sunucunun uyacağını söyler. |
| 102  | Processing           | İşlem                 |                                                              |
| 122  | Request-URL too long | Uzun Adres            | İstekte bulunun adresin(URL) uzun olduğunu belirtir.         |

### 2xx: Başarı

| 200  | OK                            | Tamam             | İsteğin ve cevabın başarılı olduğunu belirtir. |
| ---- | ----------------------------- | ----------------- | ---------------------------------------------- |
| 201  | Created                       | Oluşturuldu       | Sunucu yeni kaynak oluşturmuş.                 |
| 202  | Accepted                      | Onaylandı         | Sunucunun isteği kabul etmesi.                 |
| 203  | Non-Authoritative Information | Yetersiz Bilgi    | Başka kaynaktaki bilgi döndürülmekte.          |
| 204  | *No Content*                  | İçerik Yok        |                                                |
| 205  | *Reset Content*               | İçeriği Baştan al | Geri içerik istemciye  döndürülmemektedir.     |
| 206  | *Partial Content*             | Kısmi İçerik      | Sadece belirli kısmı  döndürülmüş.             |

### 3xx:Yönlendirme

| 300  | Multiple Choices   | Çok Seçenek                   |
| ---- | ------------------ | ----------------------------- |
| 301  | Moved Permanently  | Kalıcı Taşındı.               |
| 302  | Found              | Geçici Taşındı.               |
| 303  | See Other          | Diğerilerine Bak.             |
| 304  | Not Modified       | Güncellenmedi.                |
| 305  | Use Proxy          | Proxy Kullan.                 |
| 306  | Switch Proxy       | Proxy’e geçildi.              |
| 307  | Temporary Redirect | Geçici olarak yeniden gönder. |

### 4xx:Tarayıcı Hataları

| 400  | *Bad Request*                 | Kötü İstek                         |
| ---- | ----------------------------- | ---------------------------------- |
| 401  | *Unauthorized*                | Yetkisiz                           |
| 402  | *Payment Required*            | Ödeme Gerekli                      |
| 403  | *Forbidden*                   | Yasaklandı                         |
| 404  | *Not Found*                   | Sayfa Bulunamadı                   |
| 405  | *Method Not Allowed*          | İzin verilmeyen Metod              |
| 406  | *Not Acceptable*              | Kabul Edilemez                     |
| 407  | Proxy Authentication Required | Proxy Sunucuda login olmak gerekli |
| 408  | *İstek zaman aşamına uğradı*  | İstek zaman aşamına uğradı         |

### 5xx:Sunucu Hataları

| 500  | Internal Server Error        | Server Hatası                          |
| ---- | ---------------------------- | -------------------------------------- |
| 501  | Not Implemented              | Uygulanmamış                           |
| 502  | Bad Gateway                  | *Geçersiz Ağ Geçidi*                   |
| 503  | Service Unavailable          | *Hizmet Yok*                           |
| 504  | *Gateway Timeout*            | Zaman Aşımı                            |
| 505  | *HTTP Version not supported* | Desteklenmeyen HTTP protokol versiyonu |