# Docker for installing Symfony 

**Docker + PHP 8.0 + MySQL 8 + Nginx + Adminer**

Only for DEV, not for production!

## Setup

Add to `/etc/hosts` file lines: 
```
127.0.0.1 docker-symfony.test
127.0.0.1 adminer.test
```

Clone and run the `docker-compose`
```
git clone https://github.com/amberlex78/docker-symfony
cd docker-symfony
make init
```

Log into the PHP container
```
docker-compose exec php bash
```

## Install Symfony

To install the latest stable version:

```
symfony new . --full
or
symfony new . --full --version=stable
```

To install the current LTS version:
```
symfony new . --full --version=lts
```

To install a specific version:
```
symfony new my_project_name --full --version=5.4
```

## Check version
```
symfony console -V
```
```
bin/console -V
```
```
s -V
```
Result:
```
Symfony 5.4.1 (env: dev, debug: true)
```

## Config

```
sudo chown -R $USER:$USER project/
```
For the access to databese modify the `.env` file
```
DATABASE_URL="mysql://symfony:symfony@mysql:3306/symfony?serverVersion=8.0"
```
## Access to site
```
http://docker-symfony.test
```
