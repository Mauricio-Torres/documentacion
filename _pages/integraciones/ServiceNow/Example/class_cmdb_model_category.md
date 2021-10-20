---
title: Clase cmdb_model_category
link: "example"
---
*[Volver](../08_ejemplo.html)*  

Los atributos de la clase "cmdb_model_category" son las siguientes:

![]({{ site.baseurl }}/assets/images/service_now/class_category_model.png)

En nuestro archivo de configuración agregamos las propiedades de esta clase de la CMDB de ServiceNow

```json
   {
            "searchBy": [
                "cmdb_ci_class"
            ],
            "name": "cmdb_model_category",
            "fields": [
                {
                    "type": "string",
                    "name": "cmdb_ci_class",
                    "mappingType": "Data",
                    "mappingName": null,
                    "isRequired": true,
                    "classReference": null
                }
            ]
    },
```


```json
 {
    "dataReference": [
    {
        "name": "HardwareCategoryReference",
        "fields": [
            {
                "value": "cmdb_ci_computer",
                "fieldCMDB": "cmdb_ci_class",
                "classDevice": [
                    "Laptop",
                    "Desktop"
                ]
            }
        ]
    }
    ],
    "classCMDB": [
     {
            "searchBy": [
                "name"
            ],
            "name": "cmdb_hardware_product_model",
            "fields": [
                {
                    "type": "array",
                    "name": "cmdb_model_category",
                    "mappingType": "Reference",
                    "mappingName": "HardwareCategoryReference",
                    "isRequired": false,
                    "classReference": "cmdb_model_category"
                }    
            ]
        }
    ]
  }
```
