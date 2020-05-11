---
layout: post
title: "Steam Açılmıyor – Ubuntu"
---

Steam’ı çalıştırmak isterken hata,sorun alıyorsanız.Ubuntu veya Linux debian tabanlı sistemlerde bu açılmama sorunun nasıl giderilceğini göstereceğim.

#### Steam Açılmıyor

> **Couldn’t set up Steam data – please contact technical support**

Yukarıdaki şekilde görüldüğü gibi bir hata alıyorsanız aşağıdaki komutları terminalde sırasıyla çalıştırınız.



```
mv ~/.steam/steam/* ~/.local/share/Steam/
rmdir ~/.steam/steam
ln -s ../.local/share/Steam ~/.steam/steam
rm -rf ~/.steam/bin
```