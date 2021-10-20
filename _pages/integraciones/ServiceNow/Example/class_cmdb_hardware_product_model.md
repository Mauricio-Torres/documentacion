---
title: Clase cmdb_hardware_product_model
link: "example"
---
*[Volver](../08_ejemplo.html)*  

La clase "cmdb_hardware_product_model" relaciona la clase "cmdb_ci_computer" con un modelo, esto le permite al CI formar parte de los **Assets**

 ![]({{ site.baseurl }}/assets/images/service_now/class_cmdb_hardware_product_model.png)  

Las propiedades que tomaran un valor son:

+ **name**
+ **short_description**
+ **manufacturer**
+ **cmdb_model_category:** esta propiedad acepta valores tipo array, debido a que un dispositivo puede ser parte de diferentes categorías, como se observa en la imagen.

    Además esta propiedad hace referencia a la clase "cmdb_model_category"

    ![]({{ site.baseurl }}/assets/images/service_now/relationship_cmdb_model_category.png)  




En nuestro archivo de configuración agregamos las propiedades de esta clase de ServiceNow


```json

        {
            "searchBy": [
                "name"
            ],
            "name": "cmdb_hardware_product_model",
            "fields": [
                {
                    "type": "string",
                    "name": "manufacturer",
                    "mappingType": "Reference",
                    "mappingName": "CompanyManufactureReference",
                    "isRequired": false,
                    "classReference": "core_company"
                },
                {
                    "type": "array",
                    "name": "cmdb_model_category",
                    "mappingType": "Reference",
                    "mappingName": "HardwareCategoryReference",
                    "isRequired": false,
                    "classReference": "cmdb_model_category"
                },
                {
                    "type": "string",
                    "name": "name",
                    "mappingType": "Mapper",
                    "mappingName": null,
                    "isRequired": true,
                    "classReference": null
                },
                {
                    "type": "string",
                    "name": "short_description",
                    "mappingType": "Mapper",
                    "mappingName": null,
                    "isRequired": false,
                    "classReference": null
                }
            ]
        }

```
Adicionamos la clase "cmdb_hardware_product_model" en el archivo de configuración de la siguiente forma:

Esta clase es referida por el atributo **"model_id"** con un **"mappingName"** "HardwareProductModelReference", que referencia a la propiedad "dataReference" y "mapper" del archivo de configuración, donde colocaremos sus respectivos valores


```json
 {
     "mapper": [
         {
            "name": "HardwareProductModelReference",
            "fields": [
                {
                    "fieldDevice": "model",
                    "fieldCMDB": "name"
                },
                {
                    "fieldDevice": "model",
                    "fieldCMDB": "short_description"
                }
            ]
        }

     ],
    "dataReference": [
        {
            "name": "HardwareProductModelReference",
            "fields": [
                {
                    "fieldDevice": "model",
                    "fieldCMDB": "name"
                },
                {
                    "fieldDevice": "model",
                    "fieldCMDB": "short_description"
                }
            ]
        }     
    ],
    "classCMDB": [
        {
            "searchBy": [
                "object_id"
            ],
            "name": "cmdb_ci_computer",
            "fields": [
                {
                    "type": "string",
                    "name": "model_id",
                    "mappingType": "Reference",
                    "mappingName": "HardwareProductModelReference",
                    "isRequired": false,
                    "classReference": "cmdb_hardware_product_model"
                } 
            ]
        },
        {
            "searchBy": [
                "name"
            ],
            "name": "cmdb_hardware_product_model",
            "fields": [
                {
                    "type": "string",
                    "name": "manufacturer",
                    "mappingType": "Reference",
                    "mappingName": "CompanyManufactureReference",
                    "isRequired": false,
                    "classReference": "core_company"
                },
                {
                    "type": "array",
                    "name": "cmdb_model_category",
                    "mappingType": "Reference",
                    "mappingName": "HardwareCategoryReference",
                    "isRequired": false,
                    "classReference": "cmdb_model_category"
                },
                {
                    "type": "string",
                    "name": "name",
                    "mappingType": "Mapper",
                    "mappingName": null,
                    "isRequired": true,
                    "classReference": null
                },
                {
                    "type": "string",
                    "name": "short_description",
                    "mappingType": "Mapper",
                    "mappingName": null,
                    "isRequired": false,
                    "classReference": null
                }
            ]
        }
        
    ]
  }
```
Esta clase tiene como referencia las siguientes clases:

+  [core_company](../Example/class_core_company.html)
+  [cmdb_model_category](../Example/class_cmdb_model_category.html)

Las agregaremos en la propiedad "classCMDB" del archivo de configuración y realizaremos la configuración para "mapper" y "dataReference", de las clases que adicionamos:

```json
 {
     "mapper": [
         {
            "name": "HardwareProductModelReference",
            "fields": [
                {
                    "fieldDevice": "model",
                    "fieldCMDB": "name"
                },
                {
                    "fieldDevice": "model",
                    "fieldCMDB": "short_description"
                }
            ]
        },
        {
            "name": "CompanyManufactureReference",
            "fields": [
                {
                    "fieldDevice": "manufacturer",
                    "fieldCMDB": "name"
                }
            ]
        }

     ],
    "dataReference": [
        {
            "name": "HardwareProductModelReference",
            "fields": [
                {
                    "fieldDevice": "model",
                    "fieldCMDB": "name"
                },
                {
                    "fieldDevice": "model",
                    "fieldCMDB": "short_description"
                }
            ]
        },
       {
            "name": "CompanyManufactureReference",
            "fields": [
                {
                    "value": "false",
                    "fieldCMDB": "manufacturer",
                    "classDevice": [
                        "Laptop",
                        "Desktop",
                    ]
                },
                {
                    "value": "false",
                    "fieldCMDB": "vendor",
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
                "object_id"
            ],
            "name": "cmdb_ci_computer",
            "fields": [
                {
                    "type": "string",
                    "name": "model_id",
                    "mappingType": "Reference",
                    "mappingName": "HardwareProductModelReference",
                    "isRequired": false,
                    "classReference": "cmdb_hardware_product_model"
                } 
            ]
        },
        {
            "searchBy": [
                "name"
            ],
            "name": "cmdb_hardware_product_model",
            "fields": [
                {
                    "type": "string",
                    "name": "manufacturer",
                    "mappingType": "Reference",
                    "mappingName": "CompanyManufactureReference",
                    "isRequired": false,
                    "classReference": "core_company"
                },
                {
                    "type": "array",
                    "name": "cmdb_model_category",
                    "mappingType": "Reference",
                    "mappingName": "HardwareCategoryReference",
                    "isRequired": false,
                    "classReference": "cmdb_model_category"
                },
                {
                    "type": "string",
                    "name": "name",
                    "mappingType": "Mapper",
                    "mappingName": null,
                    "isRequired": true,
                    "classReference": null
                },
                {
                    "type": "string",
                    "name": "short_description",
                    "mappingType": "Mapper",
                    "mappingName": null,
                    "isRequired": false,
                    "classReference": null
                }
            ]
        },
        {
            "searchBy": [
                "name"
            ],
            "name": "core_company",
            "fields": [
                {
                    "type": "string",
                    "name": "name",
                    "mappingType": "Mapper",
                    "mappingName": null,
                    "isRequired": true,
                    "classReference": null
                },
                {
                    "type": "boolean",
                    "name": "manufacturer",
                    "mappingType": "Data",
                    "mappingName": null,
                    "isRequired": false,
                    "classReference": null
                },
                {
                    "type": "boolean",
                    "name": "vendor",
                    "mappingType": "Data",
                    "mappingName": null,
                    "isRequired": false,
                    "classReference": null
                }
            ]
        },
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
        }
    ]
  }
```
