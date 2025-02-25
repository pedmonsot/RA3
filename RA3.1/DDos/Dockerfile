FROM csp-waf-owasp:latest

RUN apt-get update && \
    apt-get install libapache2-mod-evasive -y

COPY ./evasive.conf /etc/apache2/mods-available/evasive.conf 

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]


