## Install LAMP

1. Update and upgrade your system
```sh
apt update && apt upgrade
```

2. Install Apache
```sh
apt install apache2
```

3. Install and setup MySQL
```sh
apt install mysql-server
```

Change root password
```sh
sudo mysql
```
```sql
mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password'; 
mysql> exit 
```
```sh
mysql_secure_installation
```

4. Install PHP component
```sh
apt install php libapache2-mod-php php-mysql
