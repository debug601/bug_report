## There is an arbitrary file upload vulnerability (RCE) in the file management module in UCMS 1.6.

vendor: http://uuu.la/

UCMS 1.6 installation package： http://uuu.la/uploadfile/file/ucms_1.6.zip

After installation, log in to the background

Click File Management
![image](https://user-images.githubusercontent.com/54017627/161382147-7f84509c-451e-4c30-87a3-3a950b186bb1.png)

Click uploadfile
![image](https://user-images.githubusercontent.com/54017627/161382174-556719a7-0022-423c-badf-e9edb4ec96cf.png)

Click to select the file, and after selecting the file ---> Click upload to upload to the "uploadfile directory"

![image](https://user-images.githubusercontent.com/54017627/161382208-2351a952-9248-45f2-93fd-0fa17a58b9c4.png)

![image](https://user-images.githubusercontent.com/54017627/161382315-911ec801-8344-4c6b-acfc-a201bb2b5e35.png)

We visit the shell.php file from the browser and upload it to the uploadfile directory of the website, and we find that the code has been executed

![image](https://user-images.githubusercontent.com/54017627/161382368-68190721-1808-456b-876e-2a27eb9f00fb.png)
