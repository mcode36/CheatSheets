# Ubuntu

## To stop Apache 2 web server, enter:
   $ /etc/init.d/apache2 stop
   or,
   $ sudo /etc/init.d/apache2 stop
   or,
   $ sudo service apache2 stop

## To start Apache 2 web server, enter:
   $ /etc/init.d/apache2 start
   or,
   $ sudo /etc/init.d/apache2 start
   or,
   $ sudo service apache2 start

## To Restart Apache 2 web server, enter:
   $ /etc/init.d/apache2 restart
   or,
   $ sudo /etc/init.d/apache2 restart
   or,
   $ sudo service apache2 restart

## To start apache service and enable it to start when system reboot
   $ systemctl start apache2
   $ systemctl enable apache2

## To disable apache2 startup at bootup
   $ sudo systemctl disable apache2

## To run apache on different port (other than default port 80)
   $ sudo vi /etc/apache2/ports.conf
   
   ~~~~
   Listen 80 <-- change to 8080
   ~~~~
   
## To check the listening ports and applications on Linux:
   $ sudo lsof -i -P -n
   $ sudo lsof -i -P -n | grep LISTEN
   

# Resources

## How to Setup Nginx as a Reverse Proxy for Apache on Ubuntu 18.04 VPS
   [link](https://www.atlantic.net/vps-hosting/how-to-setup-nginx-as-a-reverse-proxy-for-apache-on-ubuntu-18-04-vps/)