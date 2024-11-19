# ICT30018-Project-B


Testing wordpress locally
# Prerequisites

Docker: install docker here https://docs.docker.com/engine/install/

# Step 1 
Create docker compose file `compose.yml` 
```yaml
services:
  wordpress:
    image: wordpress
    restart: always
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepass
      WORDPRESS_DB_NAME: exampledb
    volumes:
      - wordpress:/var/www/html

  db:
    image: mysql:8.0
    restart: always
    environment:
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
      MYSQL_RANDOM_ROOT_PASSWORD: "1"
    volumes:
      - db:/var/lib/mysql

volumes:
  wordpress:
  db:
 ```


# Step 2:
open terminal at the file directory and run 
```
docker compose up
```
- Access End user page http://localhost:8080
- Access Admin page: http://localhost:8080/wp-admin/index.php
 
