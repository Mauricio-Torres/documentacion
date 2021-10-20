---
title: Clase core_company
link: "example"
---
*[Volver](../08_ejemplo.html)*

La clase "core_company" es requerida por diferentes clases de ServiceNow, en el archivo de configuración donde es referenciada usaremos la propiedad **"mappingName"** para designar como obtendra sus valores acordes al campo que referencie a esta clase. Los atributos que tendremos en cuenta son los siguientes:

+ Name
+ Manufacturer
+ Vendor 

 ![]({{ site.baseurl }}/assets/images/service_now/class_core_company.png)

 Los atributos de la clase "core_company" mapeados al archivo de configuración toma esta forma:

```json
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
}

```
Cabe destacar que esta clase tiene propiedades de **"mappingType" = "Data"**, este tipo de valor se registraran en la propiedad **"dataReference"** del archivo de configuración.


Escribiremos la clase en el archivo de configuración con la clase que la referencia, en este claso **"cmdb_ci_computer"**


```json
 {
    "dataReference": [

    ],
    "mapper": [

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
                    "name": "manufacturer",
                    "mappingType": "Reference",
                    "mappingName": "CompanyManufactureReference",
                    "isRequired": false,
                    "classReference": "core_company"
                },
                {
                    "type": "string",
                    "name": "company",
                    "mappingType": "Reference",
                    "mappingName": "CompanyOwnerReference",
                    "isRequired": false,
                    "classReference": "core_company"
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
        }
    ]
  }
```


La clase "core_company" es referenciada dos veces. Esto no implica que duplicaremos la clase en la propiedad **"classCMDB"**, solo la agregamos una vez; mediante la propiedad **"mappingName"** lo referenciamos a "dataReference" y "mapper" para obtener los valores de la siguiente forma:

+ CompanyManufactureReference
+ CompanyOwnerReference

```json
 {
    "dataReference": [
    ],
    "mapper": [
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
                    "name": "manufacturer",
                    "mappingType": "Reference",
                    "mappingName": "CompanyManufactureReference",
                    "isRequired": false,
                    "classReference": "core_company"
                },
                {
                    "type": "string",
                    "name": "company",
                    "mappingType": "Reference",
                    "mappingName": "CompanyOwnerReference",
                    "isRequired": false,
                    "classReference": "core_company"
                }
            ]
        }
    ]
  }
```

Para resolver el valor del **"mappingName":** "CompanyOwnerReference", lo crearemos de forma estática para todos los dispositivos relacionados con la clase **"cmdb_ci_computer"**; colocamos el valor que tomara el atributo **"fieldCMDB": "name"** de la clase "core_company" en "dataReference" de la siguiente forma: 

```json
 {
    "dataReference": [
        {
            "name": "CompanyOwnerReference",
            "fields": [
                {
                    "value": "Aranda Software",
                    "fieldCMDB": "name",
                    "classDevice": [
                        "Desktop",
                    ]
                },
                {
                    "value": "false",
                    "fieldCMDB": "manufacturer",
                    "classDevice": [
                        "Desktop",
                    ]
                },
                {
                    "value": "false",
                    "fieldCMDB": "vendor",
                    "classDevice": [
                        "Desktop",
                    ]
                }
            ]
        }
    ],
    "mapper": [

    ],
    "classCMDB": [

    ]
  }
```
Lo agregamos de esta forma porque las APIs de ADM no traen la información de la compañía del propietario.

Uniendo todas las configuraciones:




```json
 {
    "dataReference": [
       {
            "name": "CompanyManufactureReference",
            "fields": [
                {
                    "value": "false",
                    "fieldCMDB": "manufacturer",
                    "classDevice": [
                        "Desktop",

                    ]
                },
                {
                    "value": "false",
                    "fieldCMDB": "vendor",
                    "classDevice": [
                        "Desktop",
                    ]
                }
            ]
        },
        {
            "name": "CompanyOwnerReference",
            "fields": [
                {
                    "value": "Aranda Software",
                    "fieldCMDB": "name",
                    "classDevice": [
                        "Desktop",
                    ]
                },
                {
                    "value": "false",
                    "fieldCMDB": "manufacturer",
                    "classDevice": [
                        "Desktop",
                    ]
                },
                {
                    "value": "false",
                    "fieldCMDB": "vendor",
                    "classDevice": [
                        "Desktop",
                    ]
                }
            ]
        }
    ],
    "mapper": [
        {
            "name": "CompanyManufactureReference",
            "fields": [
                {
                    "fieldDevice": "manufacturer",
                    "fieldCMDB": "name"
                }
            ]
        },
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
                    "name": "manufacturer",
                    "mappingType": "Reference",
                    "mappingName": "CompanyManufactureReference",
                    "isRequired": false,
                    "classReference": "core_company"
                },
                {
                    "type": "string",
                    "name": "company",
                    "mappingType": "Reference",
                    "mappingName": "CompanyOwnerReference",
                    "isRequired": false,
                    "classReference": "core_company"
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
        }
    ]
  }
```
