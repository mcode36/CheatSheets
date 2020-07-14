# UFW - Uncomplicated Firewall

## Enable and Disable
  - To turn UFW on with the default set of rules:
	~~~~
	sudo ufw enable
	~~~~
   
  - To check the status of UFW:
	~~~~
	sudo ufw status verbose
	~~~~
   
  - To disable UFW
	~~~~
	sudo ufw disable
	~~~~
   
## Allow / Deny (specific rules)
  - Allow
	example: To allow incoming tcp and udp packet on port 53
	~~~~
	sudo ufw allow 53
	~~~~
	
	example: To allow incoming tcp packets on port 53
	~~~~
	sudo ufw allow 53/tcp
	~~~~
	
	example: To allow incoming udp packets on port 53
	~~~~
	sudo ufw allow 53/udp
	~~~~
	
  - Deny
	example: To deny tcp and udp packets on port 53
	~~~~
	sudo ufw deny 53
	~~~~
	
	example: To deny incoming tcp packets on port 53
	~~~~
	sudo ufw deny 53/tcp
	~~~~
	
	example: To deny incoming udp packets on port 53
	~~~~
	sudo ufw deny 53/udp
	~~~~
	
## Allow / Deny using service names
	example: to allow ssh by name
	~~~~
	sudo ufw allow ssh
	~~~~
	
	example: to deny ssh by name
	~~~~
	sudo ufw deny ssh
	~~~~
	
## Delete Existing Rule
  - To delete a rule, simply prefix the original rule with delete. For example, if the original rule was:
	~~~~
	ufw deny 80/tcp
	~~~~
	Use this to delete it:
	~~~~
	sudo ufw delete deny 80/tcp
	~~~~
	
## More
   check: https://help.ubuntu.com/community/UFW