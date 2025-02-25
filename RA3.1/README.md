# RA3

## Introduction

Esta práctica consiste en aplicar diversas medidas de seguridad en una web Apache alojada en un contenedor Docker. Se implementarán políticas de seguridad de contenido (CSP), firewalls de aplicaciones web (WAF), reglas OWASP y mitigación de ataques DDoS.

## Tasks

* [CSP](https://hub.docker.com/r/pedmmonsot/csp)
* [CSP + WAF](https://hub.docker.com/r/pedmmonsot/csp-waf)
* [CSP + WAF + OWASP](https://hub.docker.com/r/pedmmonsot/csp-waf-owasp)
* [CSP + WAF + OWASP + DDoS](https://hub.docker.com/r/pedmmonsot/csp-waf-owasp-ddos)

## Apartado 3.1 - Implementación de CSP

En este apartado se han aplicado las restricciones de seguridad mediante Content Security Policy (CSP). Estas políticas ayudan a prevenir ataques como Cross-Site Scripting (XSS) y otros tipos de inyección de código malicioso. Se han configurado encabezados HTTP adecuados para restringir los orígenes de carga de contenido y scripts.

![image](https://github.com/user-attachments/assets/3be7e48d-3b13-4301-ab3f-4f3e682054d7)


## Apartado 3.2 - Implementación de CSP + WAF

En este apartado se han aplicado las restricciones de CSP del apartado anterior y se ha añadido un Web Application Firewall (WAF). El WAF permite filtrar y monitorear el tráfico HTTP para bloquear posibles ataques a la aplicación web, como inyecciones SQL y accesos no autorizados.

![Muestra WAF 1](https://github.com/user-attachments/assets/1cc62586-81ad-460d-a87a-8e0237d69dda)

![image](https://github.com/user-attachments/assets/f7f12c2f-9faf-40a5-8f92-7fa7df5f13a7)


## Apartado 3.3 - Implementación de CSP + WAF + OWASP

Aquí se han mantenido las configuraciones anteriores de CSP y WAF, pero se ha incorporado un conjunto de reglas de seguridad OWASP, específicamente del OWASP ModSecurity Core Rule Set (CRS). Estas reglas proporcionan una protección adicional contra vulnerabilidades comunes en aplicaciones web, como ejecución remota de código y fugas de información.

![Muestr OWASP 1](https://github.com/user-attachments/assets/41b5d210-e88f-479b-ae9e-4deeb8eb92fd)

![Muestra OWASP](https://github.com/user-attachments/assets/80cbdd6c-9261-4bca-b154-f50e91ee4882)


## Apartado 3.4 - Implementación de CSP + WAF + OWASP + DDoS

En este último apartado, además de las configuraciones anteriores, se ha implementado un mecanismo de mitigación de ataques de denegación de servicio distribuido (DDoS). Se han establecido reglas para limitar las solicitudes por IP y analizar patrones de tráfico sospechoso, reduciendo el impacto de posibles ataques de saturación.

![MuestraDDos](https://github.com/user-attachments/assets/1cb5f33f-0396-44b0-9953-5f74cf2d6c69)

