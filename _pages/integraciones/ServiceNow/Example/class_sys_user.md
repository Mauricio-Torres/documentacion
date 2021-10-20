---
title: Clase sys_user
link: "example"
---
*[Volver](../08_ejemplo.html)*  

La clase "sys_user" referenciada por la clase "cmdb_ci_computer" asigna un usuario al dispositivo registrado, en caso que el usuario no exista lo creara.

![]({{ site.baseurl }}/assets/images/service_now/class_sys_user.png)

Mapeamos la clase "sys_user" en el archivo de configuración

```json
{
    "searchBy": [
        "user_name"
    ],
    "name": "sys_user",
    "fields": [
        {
            "type": "string",
            "name": "first_name",
            "mappingType": "Mapper",
            "mappingName": null,
            "isRequired": true,
            "classReference": null
        },
        {
            "type": "string",
            "name": "last_name",
            "mappingType": "Mapper",
            "mappingName": null,
            "isRequired": true,
            "classReference": null
        },
        {
            "type": "string",
            "name": "user_name",
            "mappingType": "Mapper",
            "mappingName": null,
            "isRequired": true,
            "classReference": null
        }
    ]
},
```

los parámetros que tomamos de la información del dispositivo son las siguientes: 

```json
 {
    "mapper": [
         {
            "name": "UserDeviceReference",
            "fields": [
                {
                    "fieldDevice": "responsibleUserName",
                    "fieldCMDB": "first_name"
                },
                {
                    "fieldDevice": "responsibleUserName",
                    "fieldCMDB": "last_name"
                },
                {
                    "fieldDevice": "userName",
                    "fieldCMDB": "user_name"
                },
                {
                    "fieldDevice": "responsibleUserEmail",
                    "fieldCMDB": "email"
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
                    "name": "assigned_to",
                    "mappingType": "Reference",
                    "mappingName": "UserDeviceReference",
                    "isRequired": false,
                    "classReference": "sys_user"
                }
            ]
        }
    ]
  }
```
