# Ubuntu

- Install MongoDB Community Edition on Ubuntu [link](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)
  1. wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
  2. echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
  3. sudo apt-get update
  4. sudo apt-get install -y mongodb-org

- Start MongoDB
~~~~
sudo systemctl start mongod
~~~~

- Check mongod service
~~~~
service mongod status
~~~~
or
~~~~
sudo systemctl status mongod
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

- Use database (this will create a new database): 
~~~~
use (db_name)
~~~~

- Show collections: 
~~~~
show collections
~~~~

- Insert new record to new database: 
~~~~
db.test.insert({"name":"test"})
~~~~

- Drop collection
db.test.drop()

## Other MongoDB configurations
- How To Configure Remote Access for MongoDB on Ubuntu 20.04
  [link](https://www.digitalocean.com/community/tutorials/how-to-configure-remote-access-for-mongodb-on-ubuntu-20-04)