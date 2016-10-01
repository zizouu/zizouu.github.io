---
layout: post
title: "iptables 초기화"
date: 2016-10-01
categories: linux
---

* content
{:toc}

## Rule Save

```bash
iptables-save > /etc/sysconfig/iptables
```

## Rule Reset

```bash
iptables -P INPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -P OUTPUT ACCEPT
iptables -t nat -F
iptables -F
iptables -X
...
```

## Rule Load

```bash
iptables-restore < /etc/sysconfig/iptables
```
