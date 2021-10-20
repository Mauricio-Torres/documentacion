---
title: Mapeo clases de ServiceNow
link: "example"
---
*[Volver](../08_ejemplo.html)*  

En la propiedad "classCMDB" se agregaran todas las clases necesarias para realizar la integración entre ADM Y la CMDB de ServiceNow, iniciaremos con la clase que representa a nuestro dispositivo "Desktop", que tiene por nombre "cmdb_ci_computer".

+ ### Colocamos el nombre de la tabla y agregamos los campos por los cuales buscaremos al CI 

```json
  "classCMDB": [
    {
      "searchBy": [
        "object_id"
      ],
      "name": "cmdb_ci_computer",
      "fields": [

      ]
    }
  ]
```

En el atributo **"object_id"** colocaremos el **id** único que fue asignado por **ADM**

 ![]({{ site.baseurl }}/assets/images/service_now/Integration_FieldsCIComputer.png)  

+ ### En la propiedad "fields" colocaremos los atributos de la clase CI

```json
{
    "type": "", 
    "name": "", 
    "mappingType": "", 
    "mappingName": "",
    "isRequired": false, 
    "classReference": "" 
}
```

#### Tipos de campos

+ "Mapper": Representa un valor ingresado directamente por el usuario, en nuestro caso tomaremos directamente el valor obtenido del API de ADM, se transforma en el tipo de valor permitido y agregamos ese valor.

+ "SysChoice": Representa un valor que hace referencia a una entidad donde se agregan datos en listas correspondientes a la clase CI (cmdb_ci_computer), el nombre de esta clase es "sys_choice" que deberemos adicionar dentro de la propiedad "classCMDB".

+ "Reference": El valor ingresado crea una relación entre el CI y la clase CMDB.

#### Campos sin referencias asociadas

**"mappingType"**: colocaremos el valor de "Mapper", determina que este valor lo tomaremos directamente del dispositivo 

**"mappingName"**: esta propiedad sirve para formar una relación entre la propiedad  **"classCMDB"** y **"mapper"** o **"dataReference"** según corresponda [ver mas](../Example/relationship_classCmdb_mapper.html)

 ![]({{ site.baseurl }}/assets/images/service_now/relation_mapper_classCmdb.png)
  


```json
[
        {
          "type": "string",
          "name": "os_version",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference" , 
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "string",
          "name": "short_description",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "disk_space",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "dns_domain",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReferenceNetwork",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "ip_address",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReferenceNetwork",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "sys_created_on",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "sys_created_on",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "unit": "MB",
          "name": "ram",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "unit": "GB",
          "name": "disk_space",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "cpu_count",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "cpu_core_count",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "object_id",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        }
      ]
```

#### Campos con referencias asociadas 

De la clase "cmdb_ci_computer" destacamos las siguientes clases con las que se relaciona:

  + "core_company": Proporciona información de la compañía que creo al dispositivo o a la compañía de la que hace parte.
  + "sys_user": Proporciona información de la persona o usuario que es responsable del dispositivo
  + "cmdb_model": Proporciona información del modelo del dispositivo, para relacionar los dispositivos tipo "Computer" ServiceNow usa la clase "cmdb_hardware_product_model" que hereda de "cmdb_model", donde se agregaran los modelos de los dispositivos si no existen.
  + "sys_choice": Su valor se obtiene a través de un "select box" 

 ![]({{ site.baseurl }}/assets/images/service_now/detail_relationship_ci_class_model.png)  

**"mappingType"**: colocaremos el valor de "Reference", determina que esta propiedad relaciona a la clase CI con otra clase. 




```json
{
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
    },
    {
        "type": "string",
        "name": "model_id",
        "mappingType": "Reference",
        "mappingName": "HardwareProductModelReference",
        "isRequired": false,
        "classReference": "cmdb_hardware_product_model"
    },
    {
        "type": "string",
        "name": "assigned_to",
        "mappingType": "Reference",
        "mappingName": "UserDeviceReference",
        "isRequired": false,
        "classReference": "sys_user"
    },
}

```

Los tipos "SysChoice" 


```json
{
    {
        "type": "string",
        "name": "os",
        "mappingType": "SysChoice",
        "mappingName": "OperatingSystemReferenced",
        "isRequired": false,
        "classReference": "sys_choice"
    },
    {
        "type": "string",
        "name": "discovery_source",
        "mappingType": "SysChoice",
        "mappingName": "DiscoverySourceReferenced",
        "isRequired": false,
        "classReference": "sys_choice"
    }
}

```

Debido a que las propiedades de la clase "cmdb_ci_computer" referencian a otras clases donde estas tienen atributos de tipo "Mapper" usaremos la propiedad **"mappingName"** para referirlas a "mapper" así estas clases usaran la referencia para resolver su valor.

  + CompanyManufactureReference
  + CompanyOwnerReference
  + HardwareProductModelReference
  + UserDeviceReference
  + OperatingSystemReferenced
  + DiscoverySourceReferenced

**NO** duplicaremos las clases en la propiedad "classCMDB", mediante el campo de "mappingName" establecemos como la clase a la que se hace referencia obtendrá los valores.


Como resultado obtendremos el siguiente JSON, con los atributos que deseamos mapear


```json
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
        },
        {
          "type": "string",
          "name": "discovery_source",
          "mappingType": "SysChoice",
          "mappingName": "DiscoverySourceReferenced",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "manufacturer",
          "mappingType": "Reference",
          "mappingName": "CompanyManufacturerReference",
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
        },
        {
          "type": "string",
          "name": "model_id",
          "mappingType": "Reference",
          "mappingName": "HardwareProductModelReference",
          "isRequired": false,
          "classReference": "cmdb_hardware_product_model"
        },
        {
          "type": "string",
          "name": "assigned_to",
          "mappingType": "Reference",
          "mappingName": "UserDeviceReference",
          "isRequired": false,
          "classReference": "sys_user"
        },
        {
          "type": "string",
          "name": "os_version",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference" , 
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "string",
          "name": "short_description",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "disk_space",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "dns_domain",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReferenceNetwork",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "ip_address",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReferenceNetwork",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "sys_created_on",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "sys_created_on",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "unit": "MB",
          "name": "ram",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "unit": "GB",
          "name": "disk_space",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "cpu_count",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "cpu_core_count",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "object_id",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        }
      ]
    }
  ]
```