---
title: Datos referenciados (DataReference)
chapter: "integracion_serviceNow"
---
*[Volver](../ServiceNow/01_configuracion.html)*  

Para registrar datos en las clases de ServiceNow es necesario contar con datos que no ofrecen las API de ADM, en algunos casos estos valores son requeridos de tal forma que el usuario debe ingresarlos de forma manual. 

Considerando esto se crea la entidad de DataReference, que representa los datos adicionales que necesita una clase para adicionar o modificar datos en ServiceNow, los datos registrados tendrán como referencia una clase ServiceNow y los dispositivos que llevarán esa configuración. Como se presenta a continuación.


```json
{
    "dataReference": [
      {
        "name": "",
        "fields": [
          {
            "value": "",
            "fieldCMDB": "",
            "classDevice": [
              "",
              ""
            ]
          }
        ]
      }
    ],
    "classMapper": [
    ],
    "classDevice": [
    ],
    "classCMDB": [
    ],
      "mapper": [
    ],
  }
```


La entidad se configura de la siguiente manera: 
+	Name: Nombre de la referencia 
+	Fields: Representa los datos adicionales necesarios para la creación o edición de registros en ServiceNow [ver más](../ServiceNow/DataReference/README.html)

