---
title: Relación entre clases CI  y dispositivos de AMD 
link: "example"
---
*[Volver](../08_ejemplo.html)*  

Para establecer la relación que existe entre los Dispositivos y las clases CI de la CMDB, estableceremos esta relación en la propiedad "classMapper" de la siguiente forma: 
```json
{
  "classMapper": [
    {
      "classDevice": [
        "Desktop",
        "Laptop"
      ],
      "classCMDB": "cmdb_ci_computer"
    }
    ]
}

```
