# Ubuntu 16.04 MySQL Setup

sudo apt-get update

sudo apt-get install -y mysql-server

mysql_secure_installation

mysqladmin -p -u root version

### Bind to server IP for security

> /etc/mysql/my.cnf
```
[mysqld]
#bind-address = db_server_ip
require_secure_transport = on
```

sudo mysql_ssl_rsa_setup --uid=mysql

### Inside mysql

CREATE DATABASE dbname;

CREATE USER 'wordpressuser'@'localhost' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON dbname.* TO 'wordpressuser'@'localhost';

CREATE USER 'wordpressuser'@'web-server_ip' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON dbname.* TO 'wordpressuser'@'web_server_ip';

FLUSH PRIVILEGES;

### Open port

sudo ufw allow 3306/tcp

## Added SSL Option to WP Config

define('MYSQL_CLIENT_FLAGS', MYSQLI_CLIENT_SSL);

### Resources

https://www.digitalocean.com/community/questions/how-to-allow-remote-mysql-database-connection

https://www.digitalocean.com/community/tutorials/how-to-set-up-a-remote-database-to-optimize-site-performance-with-mysql-on-ubuntu-16-04

