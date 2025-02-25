
FROM csp-waf:latest

RUN apt-get update && apt-get install -y libapache2-mod-security2 vim git

# Copiamos la configuración recomendada de ModSecurity
COPY ./modsecurity.conf-recommended /etc/modsecurity/modsecurity.conf

# Habilitamos el motor de reglas de ModSecurity
RUN sed -i 's/SecRuleEngine DetectionOnly/SecRuleEngine On/' /etc/modsecurity/modsecurity.conf

# Clonamos el repositorio de OWASP CRS
RUN git clone https://github.com/SpiderLabs/owasp-modsecurity-crs.git /usr/local/apache2/conf/owasp-crs

# Movemos la configuración de OWASP CRS
RUN mv /usr/local/apache2/conf/owasp-crs/crs-setup.conf.example /etc/modsecurity/crs-setup.conf && \
    mkdir -p /etc/modsecurity/rules && \
    cp -r /usr/local/apache2/conf/owasp-crs/rules/ /etc/modsecurity/

# Configuramos Apache para cargar ModSecurity con OWASP CRS
RUN echo '<IfModule security2_module>\n\
    SecDataDir /var/cache/modsecurity\n\
    Include /etc/modsecurity/modsecurity.conf\n\
    Include /etc/modsecurity/crs-setup.conf\n\
    Include /etc/modsecurity/rules/*.conf\n\
</IfModule>' > /etc/apache2/mods-enabled/security2.conf

EXPOSE 80 443

CMD ["apachectl", "-D", "FOREGROUND"]
