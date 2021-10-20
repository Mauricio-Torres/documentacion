---
title: Relación entre ADM y la CMDB de ServiceNow (Mapper)
chapter: "integracion_serviceNow"
---
*[Volver](../ServiceNow/01_configuracion.html)*  

Para realizar la integración es necesario transformar la información de los dispositivos descubiertos por ADM hacia las clases CI de ServiceNow, esto lo conseguimos mediantela entidad “Mapper” que se define como una lista de las relaciones que tendrán las clases de ServiceNow y los dispositivos en ADM.
 
  

```json
{
    "mapper": [
      {
        "name": "",
        "fields": [
          {
            "fieldDevice": "",
            "fieldCMDB": ""
          }
        ]
      }
    ],
    "dataReference": [
    ],
    "classMapper": [

    ],
    "classDevice": [

    ],
    "classCMDB": [
      
    ]
  }
```

Su configuración:
+	Fields: Representa la relación que existen entre los campos de ADM y ServiceNow [see more](../ServiceNow/Mapper/README.html)
+	Name: Nombre de referencia

