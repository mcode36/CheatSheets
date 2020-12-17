# Install MongoDB PHP Driver (Linux)

sudo apt install php-dev

sudo pecl install mongodb

add "extension=mongodb.so" to php.ini
cd /etc/php/7.2/apache2/
sudo vi php.ini


# Install MongoDB PHP Driver (Windows)
Working combination:
   httpd: Apache/2.4.43 (Win64)
   PHP  : 7.4.13, x64, Thread Safe, VC15
   MongoDB PHP Driver: 1.8.0 

Install instructions: (see https://www.php.net/manual/en/mongodb.installation.windows.php)
1. Download installation package from https://pecl.php.net/package/mongodb)
   -> CUrrent version: php_mongodb-1.8.0-7.4-ts-vc15-x64.zip
2. Extract php_mongodb.dll and put it under c:\php7\ext
3. Edit c:\php7\php.ini
   
   ; set extension dir
   extension_dir = "c:/php7/ext"
   ; Add this line in "Dynamic Extensions" section
   extension=php_mongodb.dll
   
4. Add these two into Windows PATH
   c:\php7
   c:\php7\ext
   
4. Test 
   Test 1. using DOS command prompt
   DOS> php -i
   --> Should be able to see this section 
~~~~
mongodb

MongoDB support => enabled
MongoDB extension version => 1.8.0
MongoDB extension stability => stable
libbson bundled version => 1.17.0
libmongoc bundled version => 1.17.0
libmongoc SSL => enabled
libmongoc SSL library => OpenSSL
libmongoc crypto => enabled
libmongoc crypto library => libcrypto
libmongoc crypto system profile => disabled
libmongoc SASL => enabled
libmongoc ICU => disabled
libmongoc compression => disabled
libmongocrypt bundled version => 1.0.4
libmongocrypt crypto => enabled
libmongocrypt crypto library => libcrypto
~~~~
   Test 2. Run tiny_mongo.php
   cd c:\Apache24\htdocs
   php tiny_mongo.php
   
   If the php_mongodb.dll can work with current PHP it will show HTML code on screen
   
5. Resatrt httpd, check phpinfo() result
   link to: http://localhost/info.php

** Important **
DO THIS step otherwise Apache will not load the php_mongodb.dll
>> copy libsasl.dll from c:\php7 to C:\Apache24\bin
