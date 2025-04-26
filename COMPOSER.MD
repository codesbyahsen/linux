# Composer Installation Guide for Linux (Ubuntu)

## 1. Update the Package Index
Before installing any new package, it's a good practice to update the local package index:

```bash
sudo apt update
```

## 2. Install PHP and Required Dependencies
Ensure you have PHP and the necessary extensions installed. You can install them using:

For PHP installation You can get instructions from the following:
[PHP Installation Guide](./PHP.MD)

or

```bash
sudo apt install php php-cli php-zip
```

Other Dependencies:
```bash
sudo apt install unzip curl
```

## 3. Download and Install Composer
Download the Composer installer script using `curl`:

```bash
curl -sS https://getcomposer.org/installer | php
```

Move the Composer from binary to a global location so you can use it from anywhere.
```bash
sudo mv composer.phar /usr/local/bin/composer
```

## 4. Verify the Installation
Check if Composer is installed correctly by running:
```bash
composer --version
```
