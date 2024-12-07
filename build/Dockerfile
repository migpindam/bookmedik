FROM php:8.3.14-apache

ADD bookmedik /var/www/html/
ADD script.sh /usr/local/bin/script.sh
ADD schema.sql /opt

EXPOSE 80

ENV DB_USER usuario
ENV DB_PASS hola01
ENV DB_NAME bookmedik
ENV DB_HOST db

RUN apt-get update && apt-get install -y mariadb-client
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN chmod +x /usr/local/bin/script.sh

CMD ["/usr/local/bin/script.sh"]
