---
layout: post
title: Swap Partition
date: 2017-07-03
categories: linux
---

* content
{:toc}

## Swap?

Swap Partition은 메모리가 완전 가득 찼을때 추가적으로 실행된느 프로그램을 실행 시키기 위한 예비 공간.

윈도우의 Paging과 비슷한 역할

이외에 시스템 최대 절전 모드로 진입시 메모리의 내용을 보관하는 장소로도 사용.

Swap 공간이 꼭 필요한건 아니다. 없어도 잘돌아감

## 장점

메모리의 보조공간을 제공하며 효율적 사용

최대 절전 기능을 사용할 수 있음

## 단점

크기를 동적으로 사용할 수 없어 디스크 공간을 고정으로 차지한다.

하드디스크의 소모율을 높일 수 있다.

![swap-memory](/media/linux/swap-partition.jpg)