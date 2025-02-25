FROM web-ssl:latest

RUN apt-get update && apt-get upgrade -y

COPY ./index.html /var/www/html/index.html

COPY ./apache2.conf /etc/apache2/apache2.conf

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]


