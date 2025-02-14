<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this lab, I install osTicket from the ground up using the necessary installation files. There are a few steps to take before the installation of the ticketing system. This lab is done using a Windows 10 Pro VM made on Azure. 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> (21H2)


<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/90003111-7eff-4ccb-a26a-a22967726d77)

<p>
Before installing any files, Internet Information Services (IIS) needs to be enabled. We are installing osTicket locally and it needs IIS in order to function. To turn on IIS, open the Control Panel. From the Control Panel, open Programs and and Turn Windows Features On or Off. Within this menu, expand Internet Information Services, expand Web Management Tools and enable IIS Management Console. Click and expand World Wide Web Services and expand Application Development Features. In Application Development Features, enable CGI and click ok to confirm.
</p>
<br />

![image](https://github.com/user-attachments/assets/5fe0b3a3-5b7f-404b-9a70-c0195c437ab3)

<p>
After enabling IIS, download and install PHP Manager for IIS (PHPManagerforIIS_V1.5.0.msi) from the installtion files folder. Download and install the Rewrite Module (rewrite_amd64_en-US.msi) after installing PHP Manager for IIS.
</p>
<br />

![image](https://github.com/user-attachments/assets/976b1774-6fe5-4b91-8428-7c3232d15b6d)

<p>
After installing the Rewrite Module, create a new folder/directory called C:\PHP on the Windows (C:) drive. This new folder will be used to unzip the contents from the PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) zip folder downloaded from the installation files. Extract all contents from the zip folder into the C:\PHP folder.
</p>
<br />

![image](https://github.com/user-attachments/assets/1d26140b-ccaa-484d-8153-1ecd735539ee)

<p>
Next, download and install VC_redist.x86.exe from the installation files.
</p>
<br />

![image](https://github.com/user-attachments/assets/c828aa35-0a31-471e-a638-770e2747bfca)

<p>
Next, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the installation files. Within the MySQL setup wizard, click "I agree" and select "Typical" install. Launch the Configuration Wizard after the installation. Select Standard Configuration and select Install As Windows Service and make sure Launch the MySQL Server automatically is checked. In a practical setting the credentials would be decided by the user. For the purposes of this lab, the simple credentials will be "root" for the username and password.
</p>
<br />



![image](https://github.com/user-attachments/assets/42a026ba-b3b2-455f-8e55-ebe24d64f277)

![image](https://github.com/user-attachments/assets/3c709f2d-0751-4670-b931-25ca4d88670b)

<p>
Before installing osTicket, configurations need to be made within IIS. Open IIS as an admin and select PHP Manager. Within PHP Manager, select Register new PHP version. Select Browse and select the PHP CGI executable file (php-cgi.exe) within the PHP folder created earlier in the lab. After registering the PHP version, reload the IIS server within the management console.
</p>
<br />

![image](https://github.com/user-attachments/assets/c5569f8a-8f34-4265-ad59-fa9d57b8a811)

<p>
From the installation files, download osTicket v1.15.8. Extract and copy the "upload" folder to the following path: c:\inetpub\wwwroot. Within the c:\inetpub\wwwroot folder, rename "upload" to "osTicket." Reload the IIS server afterwards.
</p>
<br />

![image](https://github.com/user-attachments/assets/0da2a7e6-c774-40c9-b281-bd11f81f29b1)

![image](https://github.com/user-attachments/assets/525267d6-77a5-45d7-a5c4-9bb5ac8c51a7)

<p>
Within the IIS console, browse to Sites -> Default -> osTicket. Click "Browse *:80" and the installation page for osTicket will now show up. Some extensions are not enabled and they will be enabled with the IIS console before installing osTicket. To do so, click on PHP Manager while in the osTicket menu in IIS. Click on "Enable or disable an extension." Enable the following extentions: php_imap.dll, php_intl.dll, php_opcache.dll.
</p>
<br />


![image](https://github.com/user-attachments/assets/b16eb274-d4d1-473b-a1bf-53bf69de0c02)

![image](https://github.com/user-attachments/assets/f5f222e1-11d8-4e21-acf2-8462f841183b)

<p>
Before continuing to install osTicket, a file needs to be renamed as well as have its permissions changed. From C:\inetpub\wwwroot\osTicket\include, rename ost-sampleconfig.php to ost-config.php. The newly named ost-config.php will have its permissions changed. Open its Properties and change the following permissions: Disable inheritence -> Remove All and New Permissions -> Everyone -> All.
</p>
<br />


![image](https://github.com/user-attachments/assets/9b366272-eab7-4835-9028-317d74bf7f83)

![image](https://github.com/user-attachments/assets/9582de56-f509-4f34-888f-061883496428)

<p>
From the installation files, download and install HeidiSQL. Create a new session with HeidiSQL and enter the password used in the installation of MySQL earlier. Within the new session, right-click on Unnamed and create a new database named osTicket. 
</p>
<br />

![image](https://github.com/user-attachments/assets/1fa1f87b-6eca-4170-9cff-818b3e8e94b5)

<p>
Within osTicket browser window, enter the necessary details to set up osTicket. For the MySQL database, use the credentials used for MySQL and HeidiSQL.
</p>
<br />


![image](https://github.com/user-attachments/assets/f8ededd9-8496-4f35-9613-be7b25d0fadd)

![image](https://github.com/user-attachments/assets/26b22abd-4095-4b45-af3b-191b64d40068)


<br />

<h2>osTicket Installed!</h2>

osTicket is now installed and ready to be used. 
