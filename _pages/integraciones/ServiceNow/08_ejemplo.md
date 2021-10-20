---
title: Ejemplo
chapter: "integracion_serviceNow"
---

El siguiente ejemplo muestra como poblar el archivo de configuración para poder realizar la integración entre ADM y la CMDB de ServiceNow.
Iniciamos con un archivo de configuración totalmente limpio como se muestra a continuación: 
```json
{
    "mapper": [
      {
        "name": "",
        "fields": [
          {
            "fieldDevice": "",
            "fieldCMDB": ""
          }
        ]
      }
    ],
    "dataReference": [
      {
        "name": "",
        "fields": [
          {
            "value": "",
            "fieldCMDB": "",
            "classDevice": [
              "",
              ""
            ]
          }
        ]
      }
    ],
    "classMapper": [
      {
        "classDevice": [

        ],
        "classCMDB": ""
      }
    ],
    "classDevice": [
      {
        "name": "",
        "fields": [
          {
            "type": "",
            "name": ""
          }
        ]
      }
    ],
    "classCMDB": [
      {
        "searchBy": [
          ""
        ],
        "name": "",
        "fields": [
          {
            "type": "",
            "name": "",
            "mappingType": "",
            "mappingName": "",
            "isRequired": false,
            "classReference": ""
          }

        ]
      }
    ]
  }
```
## 1. [MAPEO DE LOS DISPOSITIVOS (ADM)](../ServiceNow/Example/mapeo_dispositivos_adm.html)
## 2. [MAPEO DE LOS CI DE SERVICENOW](../ServiceNow/Example/mapeo_ci_servicenow.html)
  + [Class sys_user](../ServiceNow/Example/class_sys_user.html)
  + [Class core_company](../ServiceNow/Example/class_core_company.html)
  + [Class sys_choice](../ServiceNow/Example/class_sys_choice.html)
  + [Class cmdb_hardware_product_model](../ServiceNow/Example/class_cmdb_hardware_product_model.html)
  + [Class cmdb_model_category](../ServiceNow/Example/class_cmdb_model_category.html)


## 3. [RELACION ENTRE CLASSCMDB Y MAPPER](../ServiceNow/Example/relationship_classCmdb_mapper.html)
## 4. [RELACION ENTRE CLASSCMDB Y DATAREFERENCE](../ServiceNow/Example/relationship_classCmdb_dataReference.html)
## 5. [RELACION ENTRE CLASES CI Y DISPOSITIVOS](../ServiceNow/Example/relationship_class_ci_device.html)
## 6. [RELACION ENTRE CLASES CI](../ServiceNow/Example/relationship_class_ci.html)
## 6. [RESULTADO FINAL](../ServiceNow/Example/config_file.html)

