# Le decimos que OS usamos
FROM ubuntu:latest

# Instalamos Apache y los programas que necesitamos
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y apache2 && \
    a2enmod headers

# Copiamos el index a la carpeta web de Apache
COPY ./index.html /var/www/html/

# Copiamos el archivo apache2 a la carpeta correspondiente con los headers añadidos
COPY ./apache2.conf /etc/apache2/apache2.conf

# Exponer los puertos 80
EXPOSE 80

# Mantener Apache ejecutándose
CMD ["apachectl", "-D", "FOREGROUND"]




