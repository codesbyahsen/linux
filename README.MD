# List of Packages that Should be Installed

# System Essentials Tools

A curated list of essential command-line utilities and tools commonly used in Linux/Unix environments for system administration, development, and day-to-day operations.

## Git

Git is a distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

- **Primary Uses**: Source code management, version tracking, collaborative development
- **Example**: `git clone https://github.com/username/repository.git`

## Curl

Curl is a command-line tool for transferring data with URL syntax, supporting numerous protocols including HTTP, HTTPS, FTP, FTPS, SCP, SFTP, and more.

- **Primary Uses**: API testing, downloading files, web scraping
- **Example**: `curl https://example.com/api/data`

## Wget

Wget is a free utility for non-interactive download of files from the web, supporting HTTP, HTTPS, and FTP protocols.

- **Primary Uses**: Downloading files, mirroring websites, batch downloads
- **Example**: `wget https://example.com/file.zip`

## Htop

Htop is an interactive process viewer and system monitor that provides an improved visualization over the traditional top command.

- **Primary Uses**: Monitoring system resources, managing processes
- **Example**: Simply run `htop` in the terminal

## Tree

Tree is a recursive directory listing program that produces a depth-indented listing of files and directories.

- **Primary Uses**: Visualizing directory structures, generating file system reports
- **Example**: `tree /home/user/documents`

## Net-tools

Net-tools is a collection of programs for controlling the network subsystem of the Linux kernel.

- **Primary Uses**: Network configuration and troubleshooting
- **Example Tools**: `ifconfig`, `netstat`, `route`, `arp`

## Nmap

Nmap (Network Mapper) is a security scanner used to discover hosts and services on a computer network.

- **Primary Uses**: Network discovery, security auditing, port scanning
- **Example**: `nmap -sV 192.168.1.0/24`

## Zip/Unzip

Zip is a compression and file packaging utility, while unzip extracts files from ZIP archives.

- **Primary Uses**: File compression, archiving, data transfer
- **Examples**: 
  - `zip -r archive.zip directory/`
  - `unzip archive.zip`

## Tar

Tar is an archiving utility designed to store and extract files from an archive file known as a tarball.

- **Primary Uses**: File archiving, backup, software distribution
- **Example**: `tar -czvf archive.tar.gz directory/`

## Gzip

Gzip is a file compression program that replaces the original file with a compressed version having a .gz extension.

- **Primary Uses**: File compression, reducing file size for storage or transmission
- **Example**: `gzip largefile.txt`

## Rsync

Rsync is a fast, versatile file copying tool that can copy locally and to/from remote hosts.

- **Primary Uses**: Data backup, file synchronization, mirroring
- **Example**: `rsync -avz source/ destination/`

## SSH

SSH (Secure Shell) is a cryptographic network protocol for operating network services securely over an unsecured network.

- **Primary Uses**: Remote system administration, secure file transfers, tunneling
- **Example**: `ssh user@hostname`

## SSHPass

SSHPass is a tool that allows automating password authentication in SSH by supplying the password via command line or file.

- **Primary Uses**: Script automation, scheduled tasks with SSH
- **Example**: `sshpass -p "password" ssh user@hostname`
- **Security Note**: Not recommended for production environments due to security risks

## Sudo

Sudo allows users to run programs with the security privileges of another user (by default, the superuser).

- **Primary Uses**: Privilege escalation, system administration
- **Example**: `sudo apt-get update`

## Python3

Python 3 is a high-level, interpreted programming language known for its readability and versatility.

- **Primary Uses**: Scripting, automation, web development, data analysis
- **Example**: `python3 script.py`

## Python3-pip

PIP is the package installer for Python, allowing you to install and manage additional packages not included in the standard library.

- **Primary Uses**: Installing Python packages, managing dependencies
- **Example**: `pip3 install requests`

<br>
<br>
<br>

## Web Servers & Database

## Nginx

Nginx is a high-performance web server and reverse proxy server, also used as an IMAP/POP3 proxy server.
- **Primary Uses**: Serving static content, load balancing, reverse proxying
- **Example**: `sudo systemctl start nginx`
- **Configuration File**: `/etc/nginx/nginx.conf`
- **Default Document Root**: `/var/www/html`

## Apache

Apache is a widely-used open-source web server software that provides a robust and flexible platform for serving web content.
- **Primary Uses**: Hosting websites, serving dynamic content, reverse proxying
- **Example**: `sudo systemctl start apache2`
- **Configuration File**: `/etc/apache2/apache2.conf`
- **Default Document Root**: `/var/www/html`

## MySQL / MariaDB

MySQL is an open-source relational database management system (RDBMS) based on SQL (Structured Query Language). MariaDB is a fork of MySQL and is fully compatible with it.
- **Primary Uses**: Data storage, data retrieval, database management
- **Example**: `mysql -u root -p`
- **Configuration File**: `/etc/mysql/my.cnf`
- **Data Directory**: `/var/lib/mysql/`
- **Default Port**: `3306`
- **Default Socket**: `/var/run/mysqld/mysqld.sock`

## PostgreSQL

PostgreSQL is a powerful, open-source object-relational database system with an emphasis on extensibility and standards compliance.
- **Primary Uses**: Data storage, data retrieval, database management
- **Example**: `psql -U postgres`
- **Configuration File**: `/etc/postgresql/12/main/postgresql.conf`
- **Data Directory**: `/var/lib/postgresql/12/main/`
- **Default Port**: `5432`
- **Default Socket**: `/var/run/postgresql/.s.PGSQL.5432`

## Redis

Redis is an open-source, in-memory data structure store, used as a database, cache, and message broker.
- **Primary Uses**: Caching, real-time analytics, message brokering
- **Example**: `redis-cli ping`
- **Configuration File**: `/etc/redis/redis.conf`
- **Data Directory**: `/var/lib/redis/`
- **Default Port**: `6379`
- **Default Socket**: `/var/run/redis/redis.sock`
- **Default Configuration**: `/etc/redis/redis.conf`
- **Default Data Directory**: `/var/lib/redis/`

## MongoDB

MongoDB is a NoSQL database that uses a document-oriented data model, allowing for flexible and scalable data storage.
- **Primary Uses**: NoSQL data storage, real-time analytics, big data applications
- **Example**: `mongo --host localhost --port 27017`
- **Configuration File**: `/etc/mongod.conf`
- **Data Directory**: `/var/lib/mongodb/`
- **Default Port**: `27017`
- **Default Socket**: `/tmp/mongodb-27017.sock`
- **Default Configuration**: `/etc/mongod.conf`
- **Default Data Directory**: `/var/lib/mongodb/`

<br>
<br>
<br>

## Programming Languages & Tools

## Node.js

Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine, allowing for server-side scripting and building scalable network applications.
- **Primary Uses**: Web development, server-side applications, real-time applications
- **Example**: `node app.js`

## PHP

PHP is a popular general-purpose scripting language that is especially suited to web development.
- **Primary Uses**: Server-side scripting, web development, content management systems
- **Example**: `php -S localhost:8000`

<br>
<br>
<br>

## Development Tools

## VS code

Visual Studio Code is a source-code editor developed by Microsoft, featuring support for debugging, syntax highlighting, intelligent code completion, snippets, code refactoring, and embedded Git.
- **Primary Uses**: Code editing, debugging, version control
- **Example**: `code .` (to open the current directory in VS Code)

## Docker

Docker is a platform for developing, shipping, and running applications in containers, providing a consistent environment across different stages of development.
- **Primary Uses**: Containerization, application deployment, microservices architecture
- **Example**: `docker run -d -p 80:80 nginx`
- **Configuration File**: `/etc/docker/daemon.json`
- **Default Data Directory**: `/var/lib/docker/`
- **Default Socket**: `/var/run/docker.sock`
- **Default Configuration**: `/etc/docker/daemon.json`

## Kubernetes

Kubernetes is an open-source container orchestration platform for automating deployment, scaling, and management of containerized applications.
- **Primary Uses**: Container orchestration, microservices management, cloud-native applications
- **Example**: `kubectl apply -f deployment.yaml`
- **Configuration File**: `/etc/kubernetes/manifests/`
- **Default Data Directory**: `/var/lib/kubelet/`
- **Default Socket**: `/var/run/kubernetes/kubelet.sock`
- **Default Configuration**: `/etc/kubernetes/kubelet.conf`

## Terraform

Terraform is an open-source infrastructure as code software tool that provides a consistent CLI workflow to manage hundreds of cloud services.
- **Primary Uses**: Infrastructure provisioning, cloud resource management, automation
- **Example**: `terraform apply`
- **Configuration File**: `main.tf`
- **Default Data Directory**: `.terraform/`
- **Default State File**: `terraform.tfstate`
- **Default Configuration**: `terraform.tfvars`

## Postman

Postman is a collaboration platform for API development, allowing users to design, test, and document APIs.
- **Primary Uses**: API testing, documentation, collaboration
- **Example**: Use the Postman GUI to create and send requests

## PhpMyAdmin

PhpMyAdmin is a free and open-source web-based database management tool for MySQL and MariaDB.
- **Primary Uses**: Database management, SQL query execution, data import/export
- **Example**: Access via web browser at `http://localhost/phpmyadmin`
- **Configuration File**: `/etc/phpmyadmin/config.inc.php`

## Composer

Composer is a dependency manager for PHP, allowing you to manage libraries and packages in your PHP projects.
- **Primary Uses**: Dependency management, package installation
- **Example**: `composer install`

<br>
<br>
<br>

## Extras for Web Development

## Redis Cache Manager

Redis Cache Manager is a tool for managing Redis caches, providing a user-friendly interface for monitoring and controlling Redis instances.
- **Primary Uses**: Redis cache management, monitoring
- **Example**: Access via web browser at `http://localhost:8080`

## Memcached

Memcached is a high-performance, distributed memory object caching system, used to speed up dynamic web applications by alleviating database load.
- **Primary Uses**: Caching, session storage, data retrieval
- **Example**: `memcached -m 64 -p 11211 -u memcache`
- **Configuration File**: `/etc/memcached.conf`

## PHP-Redis

PHP-Redis is a PHP extension for interfacing with Redis, providing an API for interacting with Redis data structures.
- **Primary Uses**: Redis data manipulation, caching
- **Example**: `php -r "var_dump(new Redis());"`

## Certbot

Certbot is a free, automated tool for obtaining and renewing SSL/TLS certificates from the Let's Encrypt Certificate Authority.
- **Primary Uses**: SSL certificate management, HTTPS setup
- **Example**: `certbot --nginx -d example.com`

