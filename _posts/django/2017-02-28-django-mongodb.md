---
layout: post
title: "django mongoDB"
date: 2017-04-28
categories: django
---

* content
{:toc}

## django mongoDB 연동
* django-mongodb-engine을 사용
* 기본적으로 django-nonrel 버전을 사용한다. (django 1.5.11버전)
* djangotoolbox가 필요함
* engine자체가 만들어진지 오래되어 python3 지원이 안됨

```

pip install git+https://github.com/django-nonrel/django@nonrel-1.5  // nonrel버전을 설치
pip install git+https://github.com/django-nonrel/djangotoolbox      // toolbox 설치
pip install git+https://github.com/django-nonrel/mongodb-engine     // db engine 설치

```
***