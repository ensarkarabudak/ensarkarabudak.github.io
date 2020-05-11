---
layout: post
title: "Raspberry Pi Üzerinde Telegram Çalıştırmak"
tags:
  - raspberry pi
---

Bu yazımda,Rasspbery Pi cihazınız üzerinde Telegram uygulamanızı kullanarak mesaj,fotoğraf,video vb. göndermek / almak için neler yapmanız gerektiğinizden bahsedeceğim.

**1. Telegram Uygulamasını Yükleyin**

Cep telefonunuza(Android, iOS) kurun.Ayrıca Windows, macOS ve Linux masaüstü bilgisayarlarınızı da kullanabilirsiniz.

**2. Raspberry Pi Terminal Ekranını Açın**

Terminal ekranına aşağıdaki komutları sırasıyla yazarak çalıştırın.

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install libreadline-dev libconfig-dev libssl-dev lua5.2 liblua5.2-dev libevent-dev libjansson-dev libpython-dev make 

```

**3. Telegram CLI Deposunu İndirin**

Aşağıdaki depoyu indirerek yükleyin.

```bash
git clone --recursive https://github.com/vysheng/tg.git 
cd tg
./configure
make
```

Kurulum biraz sürebilir.Kurulum bittikten sonra aşağıdaki komutları yazın.

```bash
cd tg
bin/telegram-cli –k tg-server.pub –W
```

**4. Telefonunuza Bağlanın**

Şimdi telefon numaranızı soracaktır.

![image-center]({{ '/images/TelegramOnRaspberryPi/TelegramOnRaspberryPi.png' | absolute_url }}){: .align-center}

**Not:** Telefon hattınız, Türkiyeden bağlı bir servis sağlayıcıya bağlı ise başına **+90** koymayı unutmayın.

Ardından Telegram uygulamanıza bir doğrulama kodu(confirmation code) gelecektir.Bu kodu yazın.

**5. Bir Mesaj Atın**

Şimdi istedeğiniz bir kişiye mesaj atabilirsiniz.Kullanım şekli aşağıdaki gibidir.

```bash
msg <Göndereceğiniz_Kişi> <Mesaj>
```

Daha fazlası için aşağıdaki komut satırlarıyla istediğiniz şeyleri yapabilirsiniz.

#### Messaging

- **msg** <peer> Text - sends message to this peer
- **fwd** <user> <msg-seqno> - forward message to user. You can see message numbers starting client with -N
- **chat_with_peer** <peer> starts one on one chat session with this peer. /exit or /quit to end this mode.
- **add_contact** <phone-number> <first-name> <last-name> - tries to add contact to contact-list by phone
- **rename_contact** <user> <first-name> <last-name> - tries to rename contact. If you have another device it will be a fight
- **mark_read** <peer> - mark read all received messages with peer
- **delete_msg** <msg-seqno> - deletes message (not completly, though)
- **restore_msg** <msg-seqno> - restores delete message. Impossible for secret chats. Only possible short time (one hour, I think) after deletion

#### Multimedia

- **send_photo** <peer> <photo-file-name> - sends photo to peer
- **send_video** <peer> <video-file-name> - sends video to peer
- **send_text** <peer> <text-file-name> - sends text file as plain messages
- **load_photo**/load_video/load_video_thumb/load_audio/load_document/load_document_thumb <msg-seqno> - loads photo/video/audio/document to download dir
- **view_photo**/view_video/view_video_thumb/view_audio/view_document/view_document_thumb <msg-seqno> - loads photo/video to download dir and starts system default viewer
- **fwd_media** <msg-seqno> send media in your message. Use this to prevent sharing info about author of media (though, it is possible to determine user_id from media itself, it is not possible get access_hash of this user)
- **set_profile_photo** <photo-file-name> - sets userpic. Photo should be square, or server will cut biggest central square part

#### Group chat options

- **chat_info** <chat> - prints info about chat
- **chat_add_user** <chat> <user> - add user to chat
- **chat_del_user** <chat> <user> - remove user from chat
- **rename_chat** <chat> <new-name>
- **create_group_chat** <chat topic> <user1> <user2> <user3> ... - creates a groupchat with users, use chat_add_user to add more users
- **chat_set_photo** <chat> <photo-file-name> - sets group chat photo. Same limits as for profile photos.

#### Search

- **search** <peer> pattern - searches pattern in messages with peer
- **global_search** pattern - searches pattern in all messages

#### Secret chat

- **create_secret_chat** <user> - creates secret chat with this user
- **visualize_key** <secret_chat> - prints visualization of encryption key. You should compare it to your partner's one
- **set_ttl** <secret_chat> <ttl> - sets ttl to secret chat. Though client does ignore it, client on other end can make use of it
- **accept_secret_chat** <secret_chat> - manually accept secret chat (only useful when starting with -E key)

#### Stats and various info

- **user_info** <user> - prints info about user
- **history** <peer> [limit] - prints history (and marks it as read). Default limit = 40
- **dialog_list** - prints info about your dialogs
- **contact_list** - prints info about users in your contact list
- **suggested_contacts** - print info about contacts, you have max common friends
- **stats** - just for debugging
- **show_license** - prints contents of GPLv2
- **help** - prints this help
- **get_self** - get our user info

#### Card

- **export_card** - print your 'card' that anyone can later use to import your contact
- **import_card** <card> - gets user by card. You can write messages to him after that.

#### Other

- **quit** - quit
- **safe_quit** - wait for all queries to end then quit

