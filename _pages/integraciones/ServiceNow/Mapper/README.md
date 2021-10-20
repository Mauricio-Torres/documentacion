---
title: PROPIEDADES DEL MAPEADOR
link: "integraciones/ServiceNow/Mapper"
---
*[Volver](../02_relacion_entre_servicenow_adm.html)*  



Los campos de las clases CI y los campos de los dispositivos de ADM tendrán una relación uno a uno (1:1), mediante los siguientes campos. 

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
    ]
  }
```

Donde:

+ FieldCMDB: Nombre del campo en la clase CI de ServiceNow.
+ FieldDevice: Nombre de las propiedades del dispositivo en ADM