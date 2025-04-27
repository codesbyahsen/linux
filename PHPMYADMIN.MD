# Install phpMyAdmin on Ubuntu 24.04

### Dependencies
- **Nginx**: A high-performance web server.
- **MySQL**: A popular open-source relational database management system.
- **PHP**: A server-side scripting language.
- **php-fpm**: A PHP FastCGI Process Manager.
- **php-mysql**: A PHP extension for MySQL database connectivity.
- **php-xml**: A PHP extension for XML parsing.
- **php-mbstring**: A PHP extension for multibyte string handling.
- **php-curl**: A PHP extension for making HTTP requests.

## 1. First, Update Package List
Before installing any new package, it's a good practice to update the local package index:

```bash
sudo apt update
```

## 2. Install phpMyAdmin
You can install phpMyAdmin using the following command:
```bash
sudo apt install phpmyadmin
```

If You Missed Selecting Apache/Nginx (or skipped it)
No worries! Just manually link phpMyAdmin:
```bash
sudo ln -s /usr/share/phpmyadmin /var/www/html
```

## 3. Add the PHPMyAdmin Configuration:
`/etc/nginx/sites-available/default`
```
server {
     listen 80 default_server;
     listen [::]:80 default_server;

     root /var/www/html;
     index index.html index.htm index.nginx-debian.html;

     server_name _;

     location / {
             try_files $uri $uri/ =404;
     }

     # PHPMyAdmin location block
     location /phpmyadmin {
         root /usr/share/;
         index index.php;

         location ~ ^/phpmyadmin/(.+\.php)$ {
             fastcgi_pass unix:/var/run/php/php8.3-fpm.sock;  # Update to your PHP version, e.g., php8.4-fpm
             fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
             include fastcgi_params;
         }

         location ~ ^/phpmyadmin/(.*\.js|.*\.css|.*\.png|.*\.jpg|.*\.gif|.*\.ico)$ {
             root /usr/share/;
             expires 7d;
             add_header Cache-Control "public";
         }
     }
}
```

## 4. Test and Restart Nginx
```bash
sudo nginx -t
sudo systemctl restart nginx
```

## 5. Restart PHP-FPM
```bash
sudo systemctl restart php8.3-fpm
```

## 6. Access phpMyAdmin
```
http://localhost/phpmyadmin
```
