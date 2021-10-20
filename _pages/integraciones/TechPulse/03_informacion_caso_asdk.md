---
title: Relación entre los casos de ASDK V8 y los incidentes de HP TechPulse
chapter: "integracion_techPulse"
---

```json
{
   "mappers":[
      {
         "case":{
            "caseType": 0,
            "project":0,
            "service":0,
            "category":0,
            "group":0,
            "registryType":0,
            "state":[
               {
                  "name":"",
                  "value":0
               }               
            ],
            "sla":,
            "company":,
            "urgency": [
               {
                  "name": "",
                  "value": 0
               }
            ]
         }
      }
   ]
}

```

La propiedad **case** determinará el tipo de caso al que será equivalente los diferentes sub tipos de incidentes registrados en la plataforma de HP TechPulse.


En esta propiedad se registraran los **“ID”** de:

 + Tipo de caso **(caseType)**
 + Proyecto **(project)**
 + Servicio **(service)**
 + Categoria **(category)**
 + Grupo **(group)**
 + Tipo de registro **(registryType)**
 + Compañía  **(company)**
 + SLA  **(sla)**


 ![]({{ site.baseurl }}/assets/images/tech_pulse/case_asdk.png)  


 + **Estados**: Para mapear los estados buscamos su equivalencia entre los estados de HP TechPulse con los estados en ASDK V8.

    HP TechPulse proporciona los siguientes estados:


 ![]({{ site.baseurl }}/assets/images/tech_pulse/estados_techpulse.png)  


Escriba el **key estado** en la propiedad **"name"** y el **id** de su equivalente tomado de **Aranda Service Desk V8 (ASDK)** en la propiedad **value**

```json
[
    {
        "name":"NEW",
        "value":1
    },
    {
        "name":"FIXED",
        "value":13
    }
]
```


+ **Urgency**: HP TechPulse proporciona la propiedad **"prioridad"** y su equivalente con ASDK V8 es **"urgency"**. Similar a los estados agregamos su equivalente entre las dos plataformas.

    HP TechPulse proporciona los siguientes prioridades:


 ![]({{ site.baseurl }}/assets/images/tech_pulse/priority_techpulse.png)  


Escriba el **key prioridad** en la propiedad **"name"** y el **urgencyId** de su equivalente tomado de **Aranda Service Desk V8 (ASDK)** en la propiedad **value**

```json
        "urgency": [
               {
                  "name": "CRITICAL",
                  "value": 4
               },
               {
                  "name": "HIGH",
                  "value": 3
               },
               {
                  "name": "LOW",
                  "value": 2
               },
               {
                  "name": "MEDIUM",
                  "value": 2
               },
               {
                  "name": "NOT_ASSIGNED",
                  "value": -1                  
               }
            ]
```