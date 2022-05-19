# Online Car Wash Booking System v1.0 by oretnom23 has The local file contains

vendor : https://www.sourcecodester.com/php/15274/online-car-wash-booking-system-phpoop-free-source-code.html

Vulnerability File: ip/ocwbs/?p=

Vulnerability location: ip/ocwbs/?p=, p

Payload: ip/ocwbs/?p=shell
![image](https://user-images.githubusercontent.com/54017627/169309392-13f04d0c-2621-41d6-8cdb-09b94224fac7.png)

We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "
![image](https://user-images.githubusercontent.com/54017627/169309277-c851a216-faae-4c2e-8923-a07f17ba8b97.png)


And visit http://ip/ocwbs/?p=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/169309213-03caba89-8eed-44f4-9c3e-728add494072.png)
