# Wordpress Quick Notes

## Installation

See official site for quick start guide:
https://wordpress.org/support/article/how-to-install-wordpress/

1. Download and unzip the WordPress package

   cd /var/www/html
   gzip -d -c /home/mc/Downloads/wordpress-5.4.2.tar.gz | tar xvf -
   
2. Create a database for WordPress on your web server. Create user who has all privileges to access and modify the WP database
   ~~~~
   $ mysql -u root -p
   mysql> CREATE DATABASE wp_db1;
   mysql> CREATE USER 'db_user'@'localhost' IDENTIFIED BY '_new_password_';  (If user already exist, skip this step)
   mysql> GRANT ALL PRIVILEGES ON wp_db1.* TO 'db_user'@'localhost';
   ~~~~
   
3. Edit wp-config.php file
   ~~~~
   $ cd /var/www/html/wordpress
   $ cp wp-config-sample.php wp-config.php
   $ vi wp-config.php
   ~~~~
   
   Then update these three lines:
   ~~~~
   define( 'DB_NAME', 'wp_db1' );
   define( 'DB_USER', 'db_user' );
   define( 'DB_PASSWORD', '_mysql_passwd_for_db_user_' );
   ~~~~
   
4. (optional) Move all files under folder /wordpress to document root (/var/www/html)

5. open browser and link to: localhost/index.php
   
## When WP installation is on a machine that is inside a local network, not dirrectly connecting to the internet

   These two steps will solve the issues when trying to install new theme or delete plugins
   
1. Add this at the end of wp-config.php:
   ~~~~
   /** Sets up 'direct' method for wordpress, auto update without ftp */
   define('FS_METHOD','direct');
   ~~~~

2. Change everything to own by www-data:
   ~~~~
   $ cd /var/www/html
   $ sudo chown -R www-data wordpress
   ~~~~
   (Otherwise you won't be able to add/delete plug-ins and themes)
   
## Notes when using NGINX

   - Setting Permalink to "Post name" will run into a lot of "404 Not found" errors.
     Use "Plain" setup instead
	 
	 
# External Resources
- Install WordPress with Nginx Reverse Proxy to Apache on Ubuntu 18.04
  [link](https://www.cloudbooklet.com/install-wordpress-with-nginx-reverse-proxy-to-apache-on-ubuntu-18-04-google-cloud/)

- How to Install WordPress with Nginx on Ubuntu 18.04
  [link](https://linuxize.com/post/how-to-install-wordpress-with-nginx-on-ubuntu-18-04/)

- How can I configure WordPress Permalinks in Nginx?
  [link](https://nixcp.com/wordpress-permalinks-nginx/)
  