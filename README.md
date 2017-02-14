# About

This is the Git repo with multi-container Docker applications based on Alpine images
 
 
# How to use it

### Create the `vbase` shared data volume
```
docker create -v ~/mnt-docker/app:/app -v ~/mnt-docker/www-html:/var/www/html \
    -v ~/mnt-docker/github:/opt/code/git --name vbase alpine /bin/true
```

### Use docker-compose  
```
docker-compose -f web/nginx-php7-fpm-mysql.yml build
docker-compose -f web/nginx-php7-fpm-mysql.yml up -d
docker-compose -f web/nginx-php7-fpm-mysql.yml stop
docker-compose -f web/nginx-php7-fpm-mysql.yml start
docker-compose -f web/nginx-php7-fpm-mysql.yml down -v
```

# Compose files

* [web/nginx-php7-fpm-mysql.yml](web/nginx-php7-fpm-mysql.yml)