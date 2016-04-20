---
layout: post
title: "Fuel Maintenance 업데이트 스크립트"
date: 2016-04-20
categories: openstack
---

* content
{:toc}

[Mirantis - Maintenance Updates](https://docs.mirantis.com/openstack/fuel/fuel-7.0/maintenance-updates.html)

업데이트를 한줄한줄 하기에는 귀찮으므로 스크립트를 만들어서 실행시킨다.

```bash
#!/bin/bash
set -e

dockerctl backup

yum -y update
docker load -i /var/www/nailgun/docker/images/fuel-images.tar

dockerctl destroy all
dockerctl start all

puppet apply -dv /etc/puppet/modules/nailgun/examples/host-only.pp
```