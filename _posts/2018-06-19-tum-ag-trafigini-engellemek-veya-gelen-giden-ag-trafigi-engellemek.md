---
layout: post
title: "Tüm Ağ Trafiğini Engellemek veya Gelen-Giden Ağ Trafiği Engellemek"
---

Eğer bilgisayarınızdaki tüm gelen veya giden bağlantıyı engellemek istiyorsanız aşağıdaki komutları çalıştırın:

```
# iptables -F# iptables -A INPUT -j REJECT# iptables -A OUTPUT -j REJECT# iptables -A FORWARD -j REJECT
```

veya şu komutlarla da yapabilirsiniz:

```
# ipchains -F# ipchains -A input -j REJECT# ipchains -A output -j REJECT# ipchains -A forward -j REJECT
```

#### Gelen Ağ Trafiği Nasıl Engellenir?

Bilgisayarınıza gelen istek taleplerini engellemek için aşağıdaki komutları çalıştırın:

> Giden ağ trafiği etkilenmez!

```
# iptables -F INPUT# iptables -A INPUT -m state --state ESTABLISHED -j ACCEPT# iptables -A INPUT -j REJECT
```

#### Giden Ağ Trafiği Nasıl Engellenir?

Bilgisayarınızdan giden istek taleplerini engellemek için aşağıdaki komutları çalıştırın:

> Gelen ağ trafiği etkilenmez!

```
# iptables -F OUTPUT# iptables -A OUTPUT -m state --state ESTABLISHED -j ACCEPT# iptables -A OUTPUT -j REJECT
```