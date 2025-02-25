FROM csp-waf-owasp-ddos:latest

RUN apt-get update && \
    apt-get install -y openssl
    
RUN a2enmod ssl
    
RUN mkdir /etc/apache2/ssl && \
    openssl req -x509 -nodes -days 365 \
    -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key \
    -out /etc/apache2/ssl/apache.crt \
    -subj "/C=ES/ST=ES/L=CS/O=Organización/OU=Departamento/CN=www.sparkcode.com"

COPY ./index.html /var/www/html/index.html
COPY ./default-ssl.conf /etc/apache2/sites-available/default-ssl.conf

RUN a2ensite default-ssl.conf

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]


