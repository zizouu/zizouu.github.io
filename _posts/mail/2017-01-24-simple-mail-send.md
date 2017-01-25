---
layout: post
title: "Simple Mail Send Java Code - Mime Text"
date: 2017-01-24
categories: mail
---

* content
{:toc}

최소한의 헤더정보를 포함해 작성

```java
package com.zizou.mail;

import com.zizou.entity.User;

import javax.mail.*;
import javax.mail.internet.InternetAddress;
import javax.mail.internet.MimeMessage;
import java.util.Properties;
import java.util.Scanner;

public class SenMailMain {

    public static void main(String[] args) {
        User sender = new User("thecarlos@daou.co.kr");
        Scanner scan = new Scanner(System.in);

        String host = "메일호스트주소";
        String subject = "메일 발송 테스트";
        String content = "성공";
        String addr;
        int port = 25;

        System.out.println("input e-mail address : ");
        addr = scan.nextLine();

        Properties prop = new Properties();
        prop.put("mail.smtp.host", host);
        prop.put("mail.smtp.port", port);
        prop.put("mail.user", sender.getId());

        Session session;
        session = Session.getDefaultInstance(prop);
        session.setDebug(true);

        Message mimeMsg = new MimeMessage(session);
        try{
            mimeMsg.setFrom(new InternetAddress(sender.getId()));
            mimeMsg.setRecipient(Message.RecipientType.TO, new InternetAddress(addr));
            mimeMsg.setSubject(subject);
            mimeMsg.setText(content);
            Transport.send(mimeMsg);
        }catch (MessagingException e){
            e.printStackTrace();
        }
    }
}

```

- Output

```
...
input e-mail address : 
test0001@kika.terracetech.co.kr
DEBUG: setDebug: JavaMail version 1.5.6
DEBUG: getProvider() returning javax.mail.Provider[TRANSPORT,smtp,com.sun.mail.smtp.SMTPTransport,Oracle]
DEBUG SMTP: useEhlo true, useAuth false
DEBUG SMTP: trying to connect to host "kika.terracetech.co.kr", port 25, isSSL false
220 *******************************************
DEBUG SMTP: connected to host "kika.terracetech.co.kr", port: 25

EHLO zizou
250-hostname Pleased to meet you
250-SIZE 104857600
250-8BITMIME
250-HELP
250-PIPELINING
250-AUTH LOGIN PLAIN
250 ENHANCEDSTATUSCODES
DEBUG SMTP: Found extension "SIZE", arg "104857600"
DEBUG SMTP: Found extension "8BITMIME", arg ""
DEBUG SMTP: Found extension "HELP", arg ""
DEBUG SMTP: Found extension "PIPELINING", arg ""
DEBUG SMTP: Found extension "AUTH", arg "LOGIN PLAIN"
DEBUG SMTP: Found extension "ENHANCEDSTATUSCODES", arg ""
DEBUG SMTP: use8bit false
MAIL FROM:<thecarlos@daou.co.kr>
250 2.1.0 Sender <thecarlos@daou.co.kr> Ok
RCPT TO:<test0001@hostname.co.kr>
250 2.1.0 Recipient <test0001@hostname.co.kr> Ok
DEBUG SMTP: Verified Addresses
DEBUG SMTP:   test0001@hostname.co.kr
DATA
354 Start mail input; end with "<CRLF>.<CRLF>"
From: thecarlos@daou.co.kr
To: test0001@hostname.co.kr
Message-ID: <1702297201.0.1485301457929@daou-5580>
Subject: =?UTF-8?B?66mU7J28IOuwnOyGoSDthYzsiqTtirg=?=
MIME-Version: 1.0
Content-Type: text/plain; charset=UTF-8
Content-Transfer-Encoding: base64

7ISx6rO1
.
250 2.5.0 Message accepted for delivery
DEBUG SMTP: message successfully delivered to mail server
QUIT
221 2.0.0 hostname.co.kr Service closing transmission channel
...
```
