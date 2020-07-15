## List all db users
mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;

## Create user with password
mysql> CREATE USER 'db_user'@'localhost' IDENTIFIED BY '_new_password';

## Change user password
mysql> ALTER USER 'db_user'@'localhost' IDENTIFIED WITH mysql_native_password BY '_new_password';

## Grand all privileges to user
mysql> GRANT ALL PRIVILEGES ON *.* TO 'phpmyadmin'@'localhost' ;

## Grand a user full control over a specific database
mysql> GRANT ALL PRIVILEGES ON _db_name.* TO 'db_user'@'localhost';