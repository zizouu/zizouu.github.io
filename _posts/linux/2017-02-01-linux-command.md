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
***

## Yum
* yum은 자동으로 dependency관리를 해준다.
* -y 옵션은 모든 답변을 yes로 하겠다는 의미
* vs rpm : rpm은 패키지에 필요한 요소를 전부 따로 다운받아야 하나 yum은 알아서 다운

```
yum install <package-name>  // 일반 설치
yum localinstall <rpm-path> // 로컬에 rpm파일을 yum으로 설치
yum list <term>             // 특정 단어가 포함된 패키지 리스트
yum serach <package>        // 패키지 검사
```
***

## Systemctl (CentOS 7)

```
systemctl start <service-name>      // 서비스 시작
systemctl status <service-name>     // 서비스 상태 확인
systemctl restart <service-name>    // 서비스 재시작
systemctl stop <service-name>       // 서비스 중지
```
***

## Rpm

```
rpm -Uvh <package>      // 패키지 설치
rpm -e <package>        // 패키지 삭제
rpm -qa <package>       // 설치된 rpm찾기
rpm -qi <package>       // 패키지 정보
```
***

## wc
- 단어나 파일개수를 구할 때 사용
```
wc -l || --lines            // new line count
wc -w || --word             // word count
wc -m || --chars            // character count
wc -L || --max-line-lenth   // longest line length
wc -c || --bytes            // byte count
find <path/*> -type f | wc -l // file count 
```