---
layout: post
title: "장비 모니터링"
date: 2017-04-26
categories: monitoring
---

* content
{:toc}

Collectd로 각 자원의 정보를 수집한다.<br>
Influxdb로 데이터를 쌓는다.<br>
Grafana로 graphical 하게 확인<br>

# Collectd
* 장비의 CPU, Memory, Disk 등의 자원 사용 현황 데이터를 모아주는 데몬이다.
* 각 플러그인을 통해 어떤 Data를 수집할지 설정
* network 플러그인을 통해 수집한 Data를 전달
* **Config**  
    * 기본 - /etc/collectd.conf 파일
     
# Influx
* Create Database를 통해 DB를 만들고 Collectd의 network와 바운딩 해 놓으면 알아서 data가 쌓인다.
* **Config**
    * 기본 - /etc/influxdb/influxdb.conf 파일
    
# Grafana