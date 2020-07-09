# Installation

sudo apt-get update
sudo apt-get upgrade
(reboot host)
sudo apt-get install -y fail2ban

sudo systemctl start fail2ban
sudo systemctl enable fail2ban

# Configuring a jail
sudo nano /etc/fail2ban/jail.local

~~~~
[sshd]
enabled = true
port = 22
filter = sshd
logpath = /var/log/auth.log
maxretry = 3
~~~~

Then, do:
sudo systemctl restart fail2ban

# Un-ban specific IP address
sudo fail2ban-client set sshd unbanip IP_ADDRESS

# Source
https://www.techrepublic.com/article/how-to-install-fail2ban-on-ubuntu-server-18-04/