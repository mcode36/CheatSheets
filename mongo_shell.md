# Ubuntu

- Check mongod service
~~~~
service mongod status
~~~~
or
~~~~
systemctl status mongod.service
~~~~

- To start mongod
~~~~
sudo systemctl unmask mongod
sudo service mongod start
~~~~

- To start MongoDB shell
~~~~
mongo
~~~~

- mongod configuration file : /etc/mongod.conf

## Mongo shell 
- List all databases : 
~~~~
show dbs
~~~~

- Use database: 
~~~~
use (db_name)
~~~~

- Insert new record to new database: 
~~~~
db.test.insert({"name":"test"})
~~~~

