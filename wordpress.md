# Wordpress Quick Notes

## Installation

See official site for quick start guide:
https://wordpress.org/support/article/how-to-install-wordpress/

** When ** WP installation is on a machine that is inside a local network, not dirrectly connecting to the internet

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
   
## Notes when using NGINX

   - Setting Permalink to "Post name" will run into a lot of "404 Not found" errors.
     Use "Plain" setup instead