# LAMP SETUP
# Introduction
This README file provides detailed instructions for setting up a web server environment on an EC2 instance using the LAMP(Linux, Apache, MySQL, PHP) stack. The process involves installing and configuring Apache2, MySQL Server, PHP, and PHPMyAdmin. Follow the steps below for a successful setup.

## SSH Login
To access the EC2 instance, use the following SSH command:

``` bash
ssh -i "<key-pair-file-name>" <username>@<ip-address>
```


## Installing Apache2
### Update package information:

``` bash
sudo apt update
```

### Install Apache2:

``` bash
sudo apt install apache2
```
### Start Apache2 web server:

``` bash
sudo systemctl start apache2
```

### Check Apache2 status:

``` bash
sudo systemctl status apache2
```

### Enable automatic Apache2 start at boot time:

``` bash
sudo systemctl enable apache2
```


## Installing MySQL Server
### Install MySQL Server:

``` bash
sudo apt install mysql-server
```

### Check MySQL Server status:

``` bash
sudo systemctl status mysql
```


## MySQL Secure Installation

### Secure MySQL installation:

``` bash
sudo mysql_secure_installation
```

### Create a new user in MySQL:

``` sql
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'newpassword';

```
### Grant privileges to the new user:

``` sql
GRANT ALL PRIVILEGES ON *.* TO 'newuser'@'localhost' WITH GRANT OPTION;
```

### Apply changes:

``` sql
FLUSH PRIVILEGES;
```

### Exit MySQL:

``` sql
\q
```


## Installing PHP
### Install PHP along with necessary packages for integration with Apache2 and MySQL:


``` bash
sudo apt install php libapache2-mod-php php-mysql
```

### Configuring PHP
### Configure Apache2 to use PHP:

``` bash
sudo nano /etc/apache2/mods-enabled/dir.conf
```

### Edit the dir.conf file by adding index.php:

``` bash
<IfModule mod_dir.c>
    DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
```


## Installing PHPMyAdmin
### Install PHPMyAdmin:

``` bash
sudo apt install phpmyadmin
```
Note: Use MySQL user credentials created during mysql_secure_installation to log into PHPMyAdmin.

### Configure PHPMyAdmin with Apache2:

``` bash
sudo nano /etc/apache2/apache2.conf
```

### Add the following statement in apache2.conf:

``` php
Include /etc/phpmyadmin/apache.conf
```


## Creating a Web Page
### Create an 'index.php' file in '/var/www/html/' and paste a sample HTML/PHP script:

``` bash
sudo nano /var/www/html/index.php
```
This README file provides a step-by-step guide to set up an EC2 instance with Apache2, MySQL Server, PHP, and PHPMyAdmin. Follow these instructions carefully to establish a basic web server environment. For more information or troubleshooting, refer to the specific sections above.






