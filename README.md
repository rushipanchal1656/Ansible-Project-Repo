# Ansible-Project-Repo

# 📋 Playbooks Overview


# 🌐 Web Server Stacks

* Playbook Description Components Default Web Root
* LAMP.yml Deploys LAMP stack (Linux, Apache, MySQL, PHP) Apache HTTPD, MariaDB, PHP /var/www/html/
* LEMP.yml Deploys LEMP stack (Linux, Nginx, MySQL, PHP) Nginx, MariaDB, PHP-FPM /usr/share/nginx/html/
* LEMP-variable.yml LEMP stack with variables for customization Nginx, MariaDB, PHP-FPM (with vars) Configurable
* httpd-install.yml Apache HTTPD installation only Apache HTTPD /var/www/html/


# 🔧 Utility Playbooks

* Playbook Description Purpose
* all-in-one.yml Multi-purpose playbook Combined operations
* create-dir.yml Directory creation playbook File system management
* create-file.yml File creation playbook File system management
* installation-of-tree.yml Install tree command System utility installation
* ping.yml Host connectivity test Network validation

# 🚀 Quick Start


## Prerequisites

* Ansible installed on control node
* SSH access to target hosts
* Python on target hosts
* Appropriate permissions (sudo/root)

Basic Usage:

```bash

# Test connectivity

ansible-playbook ping.yml

# Deploy LAMP stack

ansible-playbook LAMP.yml

# Deploy LEMP stack

ansible-playbook LEMP.yml
```


# 📁 Detailed Playbook Information

## 1. LAMP Stack (LAMP.yml)

Deploys a complete LAMP (Linux, Apache, MySQL, PHP) web server environment.

## Features

* Installs Apache HTTPD web server
* Installs MariaDB database server
* nstalls PHP with PHP-FPM
* Creates PHP info page at /var/www/html/index.php
* Enables and starts all services

### Components

* Web Server: Apache HTTPD
* Database: MariaDB
* PHP: PHP + PHP-FPM
* Web Root: /var/www/html/

## 2. LEMP Stack (LEMP.yml)

Deploys a complete LEMP (Linux, Nginx, MySQL, PHP) web server environment.

## Features

* Installs Nginx web server
* Installs MariaDB database server
* Installs PHP with PHP-FPM
* Creates PHP info page at /usr/share/nginx/html/index.php
* Enables and starts all services

### Components

* Web Server: Nginx
* Database: MariaDB
* PHP: PHP + PHP-FPM
* Web Root: /usr/share/nginx/html/


# 🛠️ File Structure

```text
Ansible-Project-Repo/
├── LAMP.yml                    # LAMP stack deployment
├── LEMP.yml                    # LEMP stack deployment
├── LEMP-variable.yml           # LEMP with variables
├── httpd-install.yml          # Apache installation
├── all-in-one.yml             # Multi-purpose playbook
├── create-dir.yml             # Directory creation
├── create-file.yml            # File creation
├── installation-of-tree.yml   # Tree utility installation
├── ping.yml                   # Connectivity test
└── README.md                  # This documentation
```


# 🔧 Configuration
Inventory Setup
By default, playbooks target localhost. To target specific hosts:

Create an inventory file:

``` ini
[webservers]
server1 ansible_host=192.168.1.10
server2 ansible_host=192.168.1.11

[dbservers]
db1 ansible_host=192.168.1.20
Run playbook with inventory:
```

```bash
ansible-playbook -i inventory.ini LAMP.yml
Variable Customization
Edit LEMP-variable.yml or create your own variable files:
```

```yaml
---

- name: Custom LEMP Stack
  hosts: webservers
  vars:
    nginx_port: 8080
    php_version: "8.0"
    db_name: "myapp_db"
  tasks:

  # ... tasks using variables
```


# ⚡ Best Practices

1. Dry Run
Always test with --check flag first:

```bash
ansible-playbook LAMP.yml --check
```

2. Syntax Check
Validate playbook syntax:

```bash
ansible-playbook LAMP.yml --syntax-check
```

3. Verbose Output
For debugging, use verbose mode:

```bash
ansible-playbook LAMP.yml -v
# or
ansible-playbook LAMP.yml -vvv  # Most verbose
```

4. Tags
Some playbooks support tags for selective execution:

```bash
ansible-playbook LAMP.yml --tags "web,php"
```


# ✨ Author

Rushikesh Panchal

GitHub: @RushikeshPanchal1656


# ⭐ Support

If you find this repository helpful, please give it a star! ⭐
