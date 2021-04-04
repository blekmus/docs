## Setup

Install MariaDB and run the initial setup script[^1]

``` bash
sudo apt update
sudo apt install mariadb-server
sudo mysql_secure_installation
```

## Usual Process

Create db and give the `<username>` user access to the `<app-db-name>` db[^1].

``` sql
-- create db
CREATE DATABASE <app-db-name>;

-- create user
CREATE USER '<username>'@localhost IDENTIFIED BY '<password>';

-- grant privileges
GRANT ALL PRIVILEGES ON <app-db-name>.* TO '<username>'@localhost;

-- save grant changes
FLUSH PRIVILEGES;
```

## Useful Commands

### Checking

``` sql
-- display users
SELECT User FROM mysql.user;

-- display privileges
SHOW GRANTS FOR '<username>'@localhost;

-- display databases
SHOW DATABASES;
```

[^1]: https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04