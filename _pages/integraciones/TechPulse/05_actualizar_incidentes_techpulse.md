---
title: Actualizar incidentes en la plataforma HP TechPulse
chapter: "integracion_techPulse"
---

Para actualizar los incidentes en la plataforma HP TechPulse debemos registrar el API expuesta por la **Consola de Integraciones Aranda (AIC)** en la consola de configuración de ASDK V8 ([URL SERVIDOR DE CONFIGURACIONES ASDKV8]/BASDK/Main/Pages/Rules.aspx):

**ENDPOINT AIC**

**[Servidor AIC]/webhooks/99002/asdk**

![]({{ site.baseurl }}/assets/images/tech_pulse/basdk_register_rules.png)  

En la sección de reglas, configuramos el tipo de acción y condición que usaremos para que ASDK V8 ejecute la regla. 

![]({{ site.baseurl }}/assets/images/tech_pulse/add_rules_basdk.png)  

El tipo de acción que debemos escoger es **INVOCAR WEB SERVICE** Y registramos el enpoind expuesto por **AIC**

![]({{ site.baseurl }}/assets/images/tech_pulse/register_enpoint.png)  
 