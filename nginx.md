## Install nginx

   sudo apt update
   sudo apt install nginx


## Update ufw rules

   sudo ufw app list
   sudo ufw allow 'Nginx HTTP'
   sudo ufw enable
   sudo ufw status


## Start nginx service
   (optional: if apache2 is still running) /etc/init.d/apache2 stop
   sudo systemctl start nginx

## Check nginx status

   sudo systemctl status nginx

## Gracefully Restart Nginx

   sudo systemctl reload nginx

## Force Restart Nginx

   sudo systemctl restart nginx

The reload command keeps the Nginx server running as it reloads updated configuration files. If Nginx notices a syntax error in any of the configuration files, the reload is aborted and the
 server keeps running based on old config files. Reloading is safer than restarting Nginx.

The restart command will shut down the server including all related services and power it on again. Restart Nginx only when making significant configuration updates, such as changing ports
or interfaces. This command will force shut down all worker processes.

## Configure Nginx to Launch on Boot
sudo systemctl enable nginx

## Disable Nginx to Launch on Boot
sudo systemctl disable nginx


Source: https://phoenixnap.com/kb/nginx-start-stop-restart
