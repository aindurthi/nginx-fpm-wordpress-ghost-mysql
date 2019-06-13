# nginx-fpm-wordpress-ghost-mysql

# Change to the installed directory

cd nginx-fpm-wordpress-ghost-mysql/

# Generate the required files using below commands:

sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout nginx.key -out nginx.crt

sudo openssl req -out certificate.csr -key nginx.key -new

sudo openssl req -x509 -new -nodes -key nginx.key -sha256 -days 1825 -out nginx.pem

sudo openssl dhparam 2048 -out dhparam.pem

# Using the below command copy the created files into /etc/ssl/private:

cp nginx.crt nginx.key certificate.csr *.pem /etc/ssl/private

# To run in development environment:

docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d

docker exec -it containerid /bin/bash

type: hostname

Observe: "dev_server" string in hostname cmdout

type: exit

docker-compose down -v

# To run in production environment:

docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d

docker exec -it containerid /bin/bash

type: hostname

Observe: "prod_server" string in hostname cmdout

type: exit

docker-compose down -v

# Thank You

