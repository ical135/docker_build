# build image
docker build --no-cache --tag cal/php7.2.11:1.0 - < Dockerfile

# masuk ke docker exec
docker exec -it <container_name> /bin/bash

# Set php install for mysql
docker-php-ext-install mysqli pdo pdo_mysql

#host db
host : 127.0.0.1
