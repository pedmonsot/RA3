# Le decimos que imagen usamos
FROM csp:latest

# Instalamos más programas
RUN apt-get update && \
    apt-get install libapache2-mod-security2 -y && \
    a2enmod security2

COPY ./modsecurity.conf-recommended /etc/modsecurity/modsecurity.conf

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]


