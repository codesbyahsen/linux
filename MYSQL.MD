# Installing MySQL on Ubuntu 24.04

This guide provides step-by-step instructions for installing and configuring MySQL Server on Ubuntu 24.04 LTS.

## Prerequisites

- Ubuntu 24.04 LTS installed
- User with sudo privileges
- Internet connection

## Installation Steps

### 1. Update System Packages

First, update your package lists to ensure you get the latest version of MySQL:

```bash
sudo apt update
sudo apt upgrade -y
```

### 2. Install MySQL Server

Install the MySQL server package using apt:

```bash
sudo apt install mysql-server -y
```

### 3. Check MySQL Service Status

Verify that MySQL service is running:

```bash
sudo systemctl status mysql
```

If the service is not running, start it with:

```bash
sudo systemctl start mysql
```

To enable MySQL to start automatically on system boot:

```bash
sudo systemctl enable mysql
```

### 4. Secure MySQL Installation

Run the security script to improve MySQL security:

```bash
sudo mysql_secure_installation
```

This interactive script will guide you through several security options:

- Setting up a root password (highly recommended)
- Removing anonymous users
- Disabling remote root login
- Removing test database
- Reloading privilege tables

Follow the prompts and answer "Y" (yes) to the recommended security measures.

### 5. Log in to MySQL

You can log in to MySQL as the root user:

```bash
sudo mysql
```

Or if you set a password during the secure installation:

```bash
mysql -u root -p
```

### 6. Create a New MySQL User (Optional)

For better security, create a dedicated user for your applications instead of using root:

```sql
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'newuser'@'localhost';
FLUSH PRIVILEGES;
```

Replace 'newuser' and 'password' with your preferred username and a strong password.

### 7. Create a New Database (Optional)

Create a new database for your application:

```sql
CREATE DATABASE mydatabase;
```

## Configuring MySQL

### Basic Configuration

The main MySQL configuration file is located at `/etc/mysql/mysql.conf.d/mysqld.cnf`. You can edit this file to change MySQL settings:

```bash
sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
```

After making changes, restart MySQL to apply them:

```bash
sudo systemctl restart mysql
```

### Change Default Data Directory (Optional)

If you need to change the default data directory:

1. Stop MySQL service:
   ```bash
   sudo systemctl stop mysql
   ```

2. Create and prepare the new directory:
   ```bash
   sudo mkdir /new/data/directory
   sudo chown mysql:mysql /new/data/directory
   ```

3. Copy existing data to the new location:
   ```bash
   sudo rsync -av /var/lib/mysql/ /new/data/directory/
   ```

4. Update MySQL configuration in `/etc/mysql/mysql.conf.d/mysqld.cnf`:
   ```
   datadir = /new/data/directory
   ```

5. Update AppArmor configuration:
   ```bash
   sudo nano /etc/apparmor.d/tunables/alias
   ```
   Add the line:
   ```
   alias /var/lib/mysql/ -> /new/data/directory/,
   ```

6. Restart AppArmor and MySQL:
   ```bash
   sudo systemctl restart apparmor
   sudo systemctl start mysql
   ```

## Troubleshooting

### MySQL Won't Start

Check the logs for errors:

```bash
sudo journalctl -u mysql
```

### Reset Root Password

If you've forgotten the root password:

1. Stop MySQL:
   ```bash
   sudo systemctl stop mysql
   ```

2. Start MySQL with authentication disabled:
   ```bash
   sudo mysqld_safe --skip-grant-tables &
   ```

3. Connect to MySQL and reset the password:
   ```bash
   mysql -u root
   ```
   ```sql
   USE mysql;
   UPDATE user SET authentication_string=PASSWORD('newpassword') WHERE User='root';
   FLUSH PRIVILEGES;
   EXIT;
   ```

4. Restart MySQL normally:
   ```bash
   sudo killall mysqld
   sudo systemctl start mysql
   ```

## Uninstalling MySQL

If needed, you can completely remove MySQL:

```bash
sudo systemctl stop mysql
sudo apt remove --purge mysql-server mysql-client mysql-common -y
sudo apt autoremove -y
sudo apt autoclean
sudo rm -rf /var/lib/mysql
sudo rm -rf /etc/mysql
```

## Additional Resources

- [MySQL Official Documentation](https://dev.mysql.com/doc/)
- [Ubuntu MySQL Community Documentation](https://help.ubuntu.com/community/MySQL)