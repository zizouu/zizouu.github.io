---
layout: post
title: "Collectd"
date: 2017-04-26
categories: monitoring
---

* content
{:toc}

* Collectd로 각 자원의 정보를 수집한다.
* Influxdb로 데이터를 쌓는다.
* Grafana로 graphical 하게 확인

# Collectd
* 장비의 CPU, Memory, Disk 등의 자원 사용 현황 데이터를 모아주는 데몬이다.
* 각 플러그인을 통해 어떤 Data를 수집할지 설정
* network 플러그인을 통해 수집한 Data를 전달

## Config
* 기본 - /etc/collectd.conf 파일 