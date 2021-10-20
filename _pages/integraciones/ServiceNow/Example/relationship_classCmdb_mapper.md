---
title: Relación entre classCMDB y mapper 
link: "example"
---
*[Volver](../08_ejemplo.html)*  

La propiedad “mappingName" nos permite relacionar las propiedades "mapper" y "dataReference".

#### **"mapper":** 
Nos permite relacionar las propiedades del dispositivo con las propiedades de la clase CI, 

En "mapper" solo se tienen en cuenta los campos que tengan el "mappingType" de tipo "Mapper" 

Continuando con el ejemplo tomaremos las propiedades de las clases CI ServiceNow y las relacionamos con las propiedades del dispositivo ADM de la siguiente forma

 ![]({{ site.baseurl }}/assets/images/service_now/relacion_propiedades_dispositivo_clase_ci.png)  

#### Relación para "mappingType" Mapper


```json
{
  "mapper": [
   {
        "name": "DeviceComputerReferenceNetwork",
        "fields": [
            {
                "fieldDevice": "domain",
                "fieldCMDB": "dns_domain"
            },
            {
                "fieldDevice": "ipRegistred",
                "fieldCMDB": "ip_address"
            }
        ]
    },
    {
        "name": "DeviceComputerReference",
        "fields": [
            {
                "fieldDevice": "operatingSystemVersion",
                "fieldCMDB": "os_version"
            },
            {
                "fieldDevice": "name",
                "fieldCMDB": "name"
            },
            {
                "fieldDevice": "description",
                "fieldCMDB": "short_description"
            },
            {
                "fieldDevice": "serial",
                "fieldCMDB": "serial_number"
            },
            {
                "fieldDevice": "creationDate",
                "fieldCMDB": "sys_created_on"
            },
            {
                "fieldDevice": "id",
                "fieldCMDB": "object_id"
            },
            {
                "fieldDevice": "diskUsage",
                "fieldCMDB": "disk_space"
            },
            {
                "fieldDevice": "discovery_source",
                "fieldCMDB": "discovery_source"
            }
        ]
    }
  ]
}

```

#### Relación para "mappingType" Reference y SysChoice



```json
{
  "mapper": [
          {
            "name": "OperatingSystemReferenced",
            "fields": [
                {
                    "fieldDevice": "operatingSystem",
                    "fieldCMDB": "os"
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
        },
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
        },
        {
            "name": "PublisherCompanyReference",
            "fields": [
                {
                    "fieldDevice": "manufacturer",
                    "fieldCMDB": "name"
                }
            ]
        }
  ]
}

```