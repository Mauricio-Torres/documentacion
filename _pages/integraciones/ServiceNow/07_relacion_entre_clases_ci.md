---
title: Relación entre clases CI (Relationship)
chapter: "integracion_serviceNow"
---
*[Volver](../ServiceNow/01_configuracion.html)*  




Las clases CI de ServiceNow puede estar relacionados entre sí. Por ejemplo, un computador tiene discos duros, monitores, software instalado, etc. Este tipo de relaciones se pueden construir dentro de ServiceNow, como miramos en el siguiente ejemplo:
  
 ![]({{ site.baseurl }}/assets/images/service_now/RelationCMDB.png)  

Este tipo de relaciones las podemos mapear dentro de la entidad “relationship” donde tenemos las siguientes propiedades:

```json
{
  "relationship": [
    {
      "parentClassDevice": "Desktop",
      "childClassDevice": "Application",
      "relationshipType": "Used by::Uses"
    }
  ],
   "mapper": [
    ],
    "dataReference": [

    ],
    "classMapper": [

    ],
    "classDevice": [

    ],
    "classCMDB": [

    ],
}

```

+ ParentClassDevice: Nombre del dispositivo padre
+ ChildClassDevice: Nombre del dispositivo hijo o dependiente 
+ RelationshipType: tipo de relación entre los dispositivos, las relaciones se pueden consultar en la entidad “cmdb_rel_ci” [CI Relationship Types]

 ![]({{ site.baseurl }}/assets/images/service_now/relationship_name.png)  

