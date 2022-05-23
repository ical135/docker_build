# build image
docker build --tag php7.2.11:1.0 - < Dockerfile

# include gd
docker build --tag php7.2.11:2.0 - < Dockerfile

# cal ver, pdo pgsql; composer; imap
docker build --no-cache --tag cal/php7.2.11:1.0 - < Dockerfile

# masuk ke docker exec
docker exec -it <container_name> /bin/bash

# Set php install for mysql
docker-php-ext-install mysqli pdo pdo_mysql

#host db
host : 127.0.0.1
