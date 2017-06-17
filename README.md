# docker-symfony-apache

LAMP Apache + php 5.6 + MySQL + PhpMyAdmin + Varnish

## Installation

1. Create a `.env` from the `.env.dist` file.

    ```
    cp .env.dist .env
    ```

2. Change environment variable 

    ```
    # Symfony application's path (absolute or relative)
	SYMFONY_APP_PATH=/path

	# MySQL
	MYSQL_PATH=/path_mysql/.data/db
	MYSQL_ROOT_PASSWORD=root
	MYSQL_DATABASE=symfony
	MYSQL_USER=root
	MYSQL_PASSWORD=root

	# Varnish
	VARNISH_BACKEND_IP=172.18.0.1
    ```

3. Adapt the `vhost.conf` file (apache folder) at you convenience.

4. Build containers by typing : 

    ```
    $ docker-compose build
    $ docker-compose up -d
    ```

5. Update you system host file (/etc/hosts) by adding this line
    ```
    X.X.X.X      symfony.dev    
    ```

Where **X.X.X.X** corresponds to container IP address and **symfony.dev** to server name

## Commands

```
# bash commands
$ docker-compose exec php-apache bash

# MySQL commands
$ docker-compose exec db mysql -uroot -p"root"

# Delete all containers
$ docker rm $(docker ps -aq)

# Delete all images
$ docker rmi $(docker images -q)
```


