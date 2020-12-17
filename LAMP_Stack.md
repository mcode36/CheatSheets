

## Install PHP
$ sudo apt-get install php libapache2-mod-php


# External References

## How To Install Apache, MySQL & PHP on an Ubuntu 18.04 VPS or Dedicated Server
[link](https://hostadvice.com/how-to/how-to-install-apache-mysql-php-on-an-ubuntu-18-04-vps/)

# LAMP on Windows 10

Apache: 
  - Download: From apache lounge
    File: httpd-2.4.43-win64-VS16.zip
	(this version is built with the latest Windows® Visual Studio C++ 2019 aka VS16.)
	
  - Install:
    1. Extract httpd-2.4.43-win64-VS16.zip and put everything under c:\apache24
	2. Install latest 14.26.28720.3 Visual C++ Redistributable for Visual Studio 2015-2019
       - Download: Downloads\VC_redist.x64.exe, then double click to install

  - Setup apache2 (httpd.exe) as Windows service
    1. open DOS (as administrator)
	2. cd c:\apache24
	3. bin\httpd.exe -k install
	4. Double click to run ApacheMonitor.exe (in c:\apache24\bin) to manage apache service (start/stop/restart)
	   

PHP: 
  - Download VC15 x64 Thread Safe 
    File: php-7.4.9-Win32-vc15-x64.zip
	
  - Install
    Extract php-7.4.9-Win32-vc15-x64.zip, put everything under c:\php7
	
  - Setup : php.ini
    1. cd c:\php7
	2. copy php.ini-development to php.ini
	3. Edit php.ini
	   ~~~~
	   line  Content
	   ----  --------------------------------
	    757  extension_dir = "c:\php7\ext"
	    922  extension=mysqli
     ~~~~
	   
  - Setup : Apache httpd.conf
    1. cd C:\Apache24\conf
	2. Edit httpd.conf
	   ~~~~
	   Line  Content
	   ----  --------------------------------
	     37  Define SRVROOT "c:/Apache24"

		  284  <IfModule dir_module>
		  285      DirectoryIndex index.php index.html
		  286  </IfModule>

		  538  # PHP7 module
		  539  AddHandler application/x-httpd-php .php 
		  540  AddType application/x-httpd-php .php .html 
		  541  LoadModule php7_module "c:/php7/php7apache2_4.dll" 
		  542  PHPIniDir "c:/php7"
     ~~~~
	
mySQL:
  - Download: MySQL Installer 8.0.21 (from https://dev.mysql.com/downloads/installer/)
    File: mysql-installer-web-community-8.0.21.0.msi
	
  - Install: Double Click mysql-installer-web-community-8.0.21.0.msi to install
    can select "server only" option
	
	Installation path: C:\Program Files\MySQL\MySQL Server 8.0
	
	mysql root password: xxxxxxxx
  
    Add path "C:\Program Files\MySQL\MySQL Server 8.0\bin" to system path
	
  - Setup for wordpress
  
    1. open DOS command window
	   login mysql as root: mysql -u root -p
	   
	mysql> CREATE DATABASE db_name;
	mysql> CREATE USER 'user_name'@'localhost' IDENTIFIED BY 'xxxxxxxx';
	mysql> GRANT ALL PRIVILEGES ON db_name.* TO 'user_name'@'localhost';
  

Wordpress
  - Download: 
    wordpress-5.4.2.zip
	
  - Install:
    Extract the .zip file and put everything under C:\Apache24\htdocs\wproot
	
  - Setup:
    Open browser, link to http://localhost/wproot
	Follow the instructions step by step.
	
	Database name: db_name
	Username     : user_name
	Password     : xxxxxxxx
	Database Host: localhost
	Table Prefix : wp_
	
	wordpress admin account:
	Site Title: (your_Site_Title)
	Password  : xxxxxxxx
	
  - Patches
  
    Problem: "No working transports found" error when trying to install plugins
             (If LAMP+wordpress is installed on localhost not directly connecting to the internet)
	Fix:
	   1. Edit c:\php7\php.ini
	   2. Uncomment this line: extension=openssl
	   3. Restart apache service
	   
	Problem: "Fatal Error: Maximum Execution Time Exceeded" 
	         (Usually caused by low internet connection)
	Fix: 
	   1. Edit c:\php7\php.ini
	   2. Update this value to a larger number (default:30) 
	      max_execution_time = 300
	   3. Restart apache service
