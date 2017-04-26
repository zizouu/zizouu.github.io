---
layout: post
title: "Linux 명령어 모음"
date: 2017-02-01
categories: linux
---

* content
{:toc}

## Find
```

find / -name '*post*'

```
## Yum
yum은 자동으로 dependency관리를 해준다.

* 일반 설치

```

yum install <package-name>

```
***

* 로컬에 rpm파일을 yum으로 설치
```
yum localinstall <rpm-path>
```
***

## Systemctl (CentOS 7)

```

systemctl start <service-name>
systemctl status <service-name>
systemctl restart <service-name>
systemctl stop <service-name>

```