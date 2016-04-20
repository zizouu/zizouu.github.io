---
layout: post
title: "ESXi 명령어 모음"
date: 2016-04-20
categories: vmware
---

* content
{:toc}

### VM 리스트 출력

```bash
vim-cmd vmsvc/getallvms

# 간단하게 Vmid:Name 형식으로 출력
vim-cmd vmsvc/getallvms | sed '1d' | awk '{if ($1 > 0) print $1":"$2}'
```