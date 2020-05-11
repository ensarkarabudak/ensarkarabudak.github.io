---
layout: post
title: "Linux Shell(Kabuk) Nasıl Değiştirilir?"
tags:
  - linux
  - shell
---

#### Shell(Kabuk) Nedir?

Linux,UNIX,Windows gibi işletim sistemleri içerisinde kullanıcıların donanım ile iletişimini sağlayarak yönetme,haberleşme ve sistem kaynaklarını kullanma amacıyla kullanılan komutları işleten araca **Kabuk (SHELL)**denir.Windows’un sunduğu (cmd.exe), macOS için Terminal, Linux için **xterm** gibi sheller bulunur.

Öncelikle aşağıdaki üç farklı komut ile hangi shell(kabuk) üzerinde işlem yaptığımızı öğrenelim.Siz istediğinizi kullanabilirsiniz.

```
echo $SHELL `
`echo $0`
`ps -p
```

Örnek çıktı:

```
/bin/bash
```

Sisteminizde yüklü olan bütün Shell(kabuk) programları görelim.

```
$ cat /etc/shells
```

Örnek çıktı:

```
/bin/sh/bin/dash/bin/bash/bin/rbash/bin/zsh/usr/bin/zsh/usr/local/bin/fish
```

Farklı bir kabuğa nasıl **geçiş** yapabilirim?

Bunun için yukarıdaki shell çıktılarının sonundaki isimleri doğrudan terminele yazıp geçiş yapabilirsiniz.

Örneğin:

```
$ zsh
```

Aşağıda görüldüğü gibi Z Shell’e geçiş yaptım.

![image-center]({{ '/images/Shell/zsh.png' | absolute_url }}){: .align-center}



Shell(Kabuk) değiştirme işlemini Linux sistemler üzerinde kalıcı yapmak için aşağıdaki komut ile Shell’i değiştirebilirsiniz.

```
chsh -s *shell-adı* *kullanıcı-adı*
```

Shell adı kısmına cat /etc/shells komutunun çıktısından istediğinizi seçip buraya yazmalısınız.
Kullanıcı adı kısmı opsiyoneldir.İsterseniz **root** kullanıcı olarak yapabilirsiniz veya yazmayabilirsiniz.



Örnek bir kabuk değiştirme:

```
chsh -s /bin/tcsh
```

İkinci bir yolda doğrudan chsh yazıp ardından /bin/tcsh yazıp enter’a basmanız yeterli olacaktır.