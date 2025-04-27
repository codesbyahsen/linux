# MySQL Workbench Installation Guide

MySQL Workbench is a unified visual tool for database architects, developers, and DBAs. This guide provides instructions for installing MySQL Workbench on different operating systems.

## Ubuntu Installation

### Prerequisites
- Ubuntu 24.04 or later
- User with sudo privileges
- Internet connection
- MySQL Server (optional but recommended)

### Method 1: Install from Ubuntu Repository

This is the simplest method, although it may not provide the latest version.

1. Update your package list:
   ```bash
   sudo apt update
   ```

2. Install MySQL Workbench:
   ```bash
   sudo apt install mysql-workbench -y
   ```

3. Launch MySQL Workbench:
   ```bash
   mysql-workbench
   ```

### Method 2: Install from MySQL APT Repository

This method ensures you get the latest version directly from MySQL.

1. Download the MySQL APT Repository configuration package:
   ```bash
   wget https://dev.mysql.com/get/mysql-apt-config_0.8.25-1_all.deb
   ```
   Note: Check the [MySQL Downloads page](https://dev.mysql.com/downloads/repo/apt/) for the latest version number.

2. Install the MySQL APT configuration package:
   ```bash
   sudo dpkg -i mysql-apt-config_0.8.25-1_all.deb
   ```
   During installation, select "MySQL Tools & Connectors" and ensure it's set to "Enabled."

3. Update the package list:
   ```bash
   sudo apt update
   ```

4. Install MySQL Workbench:
   ```bash
   sudo apt install mysql-workbench-community -y
   ```

5. Launch MySQL Workbench:
   ```bash
   mysql-workbench
   ```

<br>
<br>

If during the dpkg step you get any missing dependency error, just run:
```bash
sudo apt --fix-broken install
```
This will fix the broken dependencies and allow you to proceed with the installation.