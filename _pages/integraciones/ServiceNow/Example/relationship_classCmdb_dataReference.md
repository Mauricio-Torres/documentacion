---
title: Relación entre classCMDB y dataReference 
link: "example"
---
*[Volver](../08_ejemplo.html)*  

En "dataReference" colocaremos los valores con "mappingType" de tipo "Data", son valores que permanecerán de manera estática y no se cambiaran durante la ejecución o cargue de los dispositivos hacia ServiceNow, se alteran si se cambia el archivo de configuración.

```json
"dataReference": [
 {
      "name": "OperatingSystemReferenced",
      "fields": [
        {
          "value": "os",
          "fieldCMDB": "lement",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        },
        {
          "value": "cmdb_ci_computer",
          "fieldCMDB": "name",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        }
      ]
    }
]
```
