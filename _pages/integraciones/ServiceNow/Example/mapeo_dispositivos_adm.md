---
title: Mapeo Dispositivos ADM
link: "integraciones/ServiceNow/DataReference"
---
*[Volver](../08_ejemplo.html)*  

Seleccionamos los dispositivos que deseamos exportar hacia la CMDB de ServiceNow, en este caso solo tendremos en cuenta los dispositivos de tipo "Desktop".

 ![]({{ site.baseurl }}/assets/images/service_now/device_adm/detail_device.png)  


En la propiedad "classDevice" escribimos las propiedades del dispositivo con su nombre y tipo de propiedad de la siguiente manera

```json
"classDevice": [
        {
            "name": "Desktop",
            "fields": [
                {
                    "type": "string",
                    "name": "name"
                },
                {
                    "type": "long",
                    "name": "diskTotal"
                },
                {
                    "type": "long",
                    "name": "totalRam"
                }
                ...
            ]
        }
    ]
```
A continuación, listamos las propiedades de los dispositivos 

```
{
      "cpuCore": (type: int),
      "cpuLogic": (type: int),
      "diskAvailable": (type: int),
      "diskTotal": (type: long),
      "macAddressRegister": (type: string),
      "operationSystem": (type: string),
      "totalRam": (type: long),
      "agentProfile": (type: string),
      "agentVersion": (type: string),
      "completeIpAddress": (type: string),
      "creationDate": (type: date),
      "daysSinceLastInventory": (type: int),
      "description": (type: string),
      "discovery": (type: boolean),
      "diskUsage": (type: long),
      "domain": (type: string),
      "id": (type: int),
      "ipRegistred": (type: string),
      "lastCommunicationUpdate": (type: date),
      "lastInventory": (type: date),
      "manufacturer": (type: string),
      "memoryUsage": (type: long),
      "model": (type: string),
      "name": (type: string),
      "operatingSystem": (type: string),
      "operatingSystemVersion": (type: string),
      "responsibleUserEmail": (type: string),
      "responsibleUserId": (type: int),
      "responsibleUserName": (type: string),
      "serial": (type: string),
      "status": (type: string),
      "type": (type: string),
      "userName": (type: string),
      "virtualization": (type: string),
      "vpro": (type: boolean)
    }
```