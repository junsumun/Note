# MySQL Note


## MySQL Set up

### MySQL Set up with Docker
1. Download [Docker Desktop](https://www.docker.com/products/docker-desktop).

2. Create a docker-compose.yml file.
   ```yml
    version: "3.3"
    services:
      db:
        image: mysql:8.0.21 
        command: --default-authentication-plugin=mysql_native_password
        restart: always
        container_name: mysql-local
        ports:
          - "3306:3306"
        environment:
          MYSQL_ROOT_PASSWORD: mysql_local
          MYSQL_DATABASE: mysql_local
          MYSQL_USER: mysql_local
          MYSQL_PASSWORD: mysql_local
   ```
   > ```command: --default-authentication-plugin=mysql_native_password```
   > 
   > To use legacy authentication in MySQL
   > 
   >[How to use legacy authentication in MySQL - Medium Page](https://medium.com/codespace69/mysql-8-0-client-does-not-support-authentication-protocol-requested-by-server-consider-8afadc2385e2)
