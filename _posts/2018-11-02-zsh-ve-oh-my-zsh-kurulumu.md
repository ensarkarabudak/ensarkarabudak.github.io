---
layout: post
title: "ZSH ve Oh My ZSH Kurulumu"
tags:
  - zsh
  - sheel
  - linux
---

İlk olarak ZSH kurulumunu yapalım.

```bash
sudo apt-get install zsh
```

Ardından default shell’imizi ZSH olarak ayarlayalım.

```bash
chsh -s /bin/zsh root
```

SHELL değiştirme detaylı anlatımı için [Linux Shell(Kabuk) Nasıl Değiştirilir?](http://ensarkarabudak.com/gnu-linux/linux-shell-kabuk-nasil-degistirilir/) yazımı okuyabilirsiniz.

Oh my ZSH kurulumunu yapalım.

```bash
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

Eğer terminaliniz değişmediyse aşağıdaki kodu **~/.zshrc**  dosyasının alt kısmına yapıştırın.

```
if [[ $- == i ]]; then export SHELL=zsh 
   exec zsh -l a
fi
```

Shell temasını değiştirmek için vi ~/.zshrc dosyasını açın.

**ZSH_THEME=”robbyrussell”** kısmını **ZSH_THEME=”agnoster”** olarak değiştirin. Siz isterseniz istediğiniz temayı bularak ismini buraya yazabilirsiniz.

Kaydedip çıktıktan sonra **source ~/.zshrc** yazıp kullanabilirsiniz.

Eğer font ayarlarını beğenmediyseniz aşağıdaki komutları çalıştırın.

```
sudo apt-get install fonts-powerline
cd fonts
./install.sh
```

### Oh My ZSH eklenti kurulumu

```
vi ~/.zshrc
```

komutuyla dosyamızı açalım ve  **plugins=(git)** kısmı bizim eklentilerimizin olduğu satırdır.Siz isterseniz [buradan](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins)istediğiniz eklentinin ismini alıp git’ten sonra boşluk bırakarak yazabilirsiniz.Örneğin vscode eklentsini ekleyelim. **plugins=(git vscode)**  şeklinde yazıp kaydedip çıktıktan sonra **source ~/.zshrc** komutunu çalıştırın.

Kurulum tamamlanmıştır. 