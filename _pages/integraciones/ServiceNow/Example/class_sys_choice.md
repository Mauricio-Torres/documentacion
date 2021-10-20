---
title: Clase sys_choice
link: "example"
---
*[Volver](../08_ejemplo.html)*  

Los valores tipo SysChoice se agregan en la clase **"sys_choice"**, la entidad pide los siguientes atributos para realizar un registro: 

![]({{ site.baseurl }}/assets/images/service_now/class_sys_choice.png)

Mapeando la clase a nuestro archivo de configuración 

```json

{
    "searchBy": [
        "name",
        "value"
    ],
    "name": "sys_choice",
    "fields": [
        {
            "type": "string",
            "name": "element",
            "mappingType": "Data",
            "mappingName": null,
            "isRequired": true,
            "classReference": null
        },
        {
            "type": "string",
            "name": "name",
            "mappingType": "Data",
            "mappingName": null,
            "isRequired": true,
            "classReference": null
        },
        {
            "type": "string",
            "name": "value",
            "mappingType": "Mapper",
            "mappingName": null,
            "isRequired": false,
            "classReference": null
        },
        {
            "type": "string",
            "name": "label",
            "mappingType": "Mapper",
            "mappingName": null,
            "isRequired": false,
            "classReference": null
        }
    ]
}
```

Para adicionar estos valores en nuestra configuración, el valor de **“value”** y **“label”** son los únicos que tomaremos del dispositivo, los otros atributos los registraremos en **"dataReference"**, 

```json
 {
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
    ],
    "mapper": [
        {
            "name": "OperatingSystemReferenced",
            "fields": [
                {
                    "fieldDevice": "operatingSystem",
                    "fieldCMDB": "os"
                },
                {
                    "fieldDevice": "operatingSystem",
                    "fieldCMDB": "label"
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
                    "name": "os",
                    "mappingType": "SysChoice",
                    "mappingName": "OperatingSystemReferenced",
                    "isRequired": false,
                    "classReference": "sys_choice"
                }]
        }
    ]
  }
```

Donde: 

+ **"fieldCMDB": "name"**: el atributo "name", referencia la clase con la que se relacionara "sys_choice"

+ **"fieldCMDB": "lement"**: el atributo "element" tomara el valor del campo al que refiere, debido a que el campo que lo refiere es **"os"** de la clase "cmdb_ci_computer", asignamos su valor como "os"


  ![]({{ site.baseurl }}/assets/images/service_now/class_sys_choice_reference_os.png)  
