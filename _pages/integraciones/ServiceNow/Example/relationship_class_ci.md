---
title: Relación entre clases CI
link: "example"
---

Debido a que un dispositivo puede formar relaciones de pertenencias por ejemplo un Computador tiene Monitores o Aplicaciones (Software), Discos, etc. Establecemos esas relaciones en la propiedad "relationship" 

+ "relationshipType" : Determina el tipo de relación que formaran los dispositivos, está determinado por la CMDB de ServiceNow.

```json
{
  "relationship": [
    {
      "parentClassDevice": "Desktop",
      "childClassDevice": "Application",
      "relationshipType": "Used by::Uses"
    },
    {
      "parentClassDevice": "Desktop",
      "childClassDevice": "Disk",
      "relationshipType": "Used by::Uses"
    },
    {
      "parentClassDevice": "Desktop",
      "childClassDevice": "LogicalDisk",
      "relationshipType": "Used by::Uses"
    }
  ]
}
```
