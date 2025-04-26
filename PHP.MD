# Install Multiple PHP Versions on Ubuntu and Manage Them with update-alternatives

## 1. Update the Package Index
Before installing any new package, it's a good practice to update the local package index:

```bash
sudo apt update
```

## 2. Add the PHP Repository
First, add the Ondřej Surý PPA, which contains multiple PHP versions:
    
```bash
sudo apt install software-properties-common -y
sudo add-apt-repository ppa:ondrej/php
sudo apt update
```

## 3. Install PHP Versions
You can install multiple PHP versions by specifying the version number. For example, to install PHP 7.4, 8.0, and 8.1, run:

```bash
sudo apt install -y php7.4 php7.4-cli php7.4-fpm php7.4-common php7.4-mysql php7.4-zip php7.4-gd php7.4-mbstring php7.4-curl php7.4-xml php7.4-pdo
sudo apt install -y php8.0 php8.0-cli php8.0-fpm php8.0-common php8.0-mysql php8.0-zip php8.0-gd php8.0-mbstring php8.0-curl php8.0-xml php8.0-pdo
sudo apt install -y php8.1 php8.1-cli php8.1-fpm php8.1-common php8.1-mysql php8.1-zip php8.1-gd php8.1-mbstring php8.1-curl php8.1-xml php8.1-pdo
```

## 4. Configure update-alternatives for PHP

```bash
sudo update-alternatives --install /usr/bin/php php /usr/bin/php7.4 74
sudo update-alternatives --install /usr/bin/php php /usr/bin/php8.0 80
sudo update-alternatives --install /usr/bin/php php /usr/bin/php8.1 81
```

## 5. Switch Between PHP Versions
To switch between installed PHP versions, use the following command:

```bash
sudo update-alternatives --config php
```

## 6. Verify the Active PHP Version
After switching, you can verify the active PHP version by running:

```bash
php -v
```

## (Optional) Switch php-fpm Versions
Stop the old version:
```bash
sudo systemctl stop php7.4-fpm
```
Start the new one:
```bash
sudo systemctl start php8.1-fpm
```
Check status of FPM:
```bash
sudo systemctl status php8.1-fpm
```

## Conclusion
You have successfully installed multiple PHP versions on your Ubuntu system and can switch between them using `update-alternatives`. This setup allows you to run different applications with different PHP versions as needed.