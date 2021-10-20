---
title: Autenticación 
chapter: "integracion_techPulse"
---

El primer paso para la integración con HP TechPulse es la creación de una cuenta, registrar una aplicación y su respectiva aprobación, donde obtendremos las credenciales.

- **Obtener credenciales**: La plataforma nos proporcionara un **API Client ID** y el **API Secret**

 ![]({{ site.baseurl }}/assets/images/tech_pulse/credentials_techpulse.png)  

- **Obtener Refresh Token**: Las API de HP TechPulse requieren una autorización bajo el protocolo OAuth 2.0.

De la documentación de HP TechPulse obtenemos los siguientes “endpoints”:

+ **URL Autorización**

    **Para clientes de EE. UU.**

    https://daas.api.hp.com/oauth/v1/authorize


    **Para clientes de la UE**

    https://eu.daas.api.hp.com/oauth/v1/authorize


+ **Access Token URL**

    **Para clientes de EE. UU.**
    https://daas.api.hp.com/oauth/v1/token


    **Para clientes de la UE**
    https://eu.daas.api.hp.com/oauth/v1/token

Para obtener el "refresh token" podemos usar cualquier API que proporciona HP TechPulse, para el ejemplo tomamos el siguiente endpoint 

**(“[Server_TechPulse]/analytics/v1/reports/hwinv/details/type/grid”)**


La solicitud se realizara con los servidores de E.U. **[https://daas.api.hp.com]**

Realizamos la petición con la ayuda de la aplicación **Postman** y obtenemos el refresh token



 ![]({{ site.baseurl }}/assets/images/tech_pulse/postman_oauth_techpulse.png)  

La petición nos da como resultado 

```json

{
    "access_token": "9vVLTv496kRmIAkfRwDvAUAr271T",
    "scope": "Read",
    "token_type": "Bearer",
    "refresh_token": "D9HhoBelDMPizflefEMRNztIlrnEflUP",
    "expires_in": 1799999
}
```

El token obtenido lo registramos en las credenciales solicitadas por el **Centro de Integraciones Aranda (AIC)** [ver más](../../funcionalidades/02_configuracion.html)

#### **Duración del token de acceso**

Los tokens de acceso permanecen válidos hasta la cantidad de segundos devueltos en el campo expires_in en la respuesta de la API.




**PARA MAS INFORMACIÓN DE LA AUTENTICACIÓN CON HP TECHPULSE VISITE SU PAGINA OFICIAL**
