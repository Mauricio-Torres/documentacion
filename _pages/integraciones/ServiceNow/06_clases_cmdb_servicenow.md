---
title: Clases de la CMDB de ServiceNow (ClassCMDB)
chapter: "integracion_serviceNow"
---
*[Volver](../ServiceNow/01_configuracion.html)*  

La CMDB de ServiceNow contiene clases de sistema [CI Class Manager], que almacenan datos sobre elementos de configuración (CI). Cada tipo de CI (clase CI) tiene diferentes atributos. Que representan alguna propiedad del dispositivo registrado.


 ![]({{ site.baseurl }}/assets/images/service_now/CI_Class.png)  

Donde:
1. Atributos de la clase CI
2. Nombre de la clase CI



#### **Configuración** 

```json
{
      "classCMDB": [
      {
        "searchBy": [
          ""
        ],
        "name": "",
        "fields": [
          {
            "unit":"",
            "type": "",
            "name": "",
            "mappingType": "",
            "mappingName": "",
            "isRequired": false,
            "classReference": ""
          }

        ]
      }
    ],
    "mapper": [
    ],
    "dataReference": [
    ],
    "classMapper": [

    ],
    "classDevice": [
    ]

  }
```


Para realizar la integración registraremos en el JSON las siguientes propiedades: 
+	Fields: Lista de los atributos o propiedades de la clase registrada. [ver más](../ServiceNow/ClassCMDB/README.html)
+	Name: Nombre de la clase en ServiceNow.
+	Alias: Dentro de la CMDB de ServiceNow una clase CI puede servir para mapear diferentes CI, como es el caso de la clase “cmdb_ci_disk”, que sirve para mapear Discos Duros, Memorias RAM, etc. El Alias es un seudónimo que se le da a la clase CI, para poder tener una relación 1:1 entre dispositivos de ADM y la CMDB. 
+	SearchBy: Representa los campos por los que se puede buscar en la clase de ServiceNow
