# nginx-fpm-wordpress-ghost-mysql
This repository is used to connect nginx,php-fpm,wordpress,ghost,mysql,mariadb containers.

generate the required files using below commands:

sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout nginx.key -out nginx.crt

sudo openssl dhparam 2048 -out dhparam.pem

sudo openssl req -out certificate.csr -key nginx.key -new

sudo openssl req -x509 -new -nodes -key nginx.key -sha256 -days 1825 -out nginx.pem

Using the below command copy the created files into /etc/ssl/private:

cp nginx.* certificate.csr *.pem /etc/ssl/private



