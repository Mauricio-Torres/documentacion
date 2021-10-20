---
title: Atributos del dispositivo (fields)
link: "integraciones/ServiceNow/ClassDevice"
---
*[Volver](../05_dispositivos_adm.html)*  
Representa las propiedades de los dispositivos de ADM: tipo de valor, nombre del campo.
+	Type: Tipo de valor que tiene la propiedad del dispositivo registrado en la plataforma de ADM, estos valores pueden ser:

    +	int,
    +	long,
    +	float,
    +	decimal,
    +	boolean,
    +	date,
    +	string

+	Name: Nombre de la propiedad del dispositivo

#### **PROPIEDADES DE LOS DISPOSITIVOS**



#### DEVICE: Laptop, Desktop, Router, Switch, Server, Printer.

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

#### DISK

```
{
      "busType": (type: string),
      "diskId":(type: int),
      "features": (type: string),
      "freeSpace":(type: long),
      "id": (type: int),
      "manufacturer": (type: string),
      "mediaType": (type: string),
      "model": (type: string),
      "pnpDeviceId": (type: string),
      "serial": (type: string),
      "size": (type: long),
      "usedSpace": (type: long),
}

```


#### DISPLAY

```
{
    "date": (type: date),
    "manufacturer": (type: string),
    "Model": (type: string),
    "name": (type: string),
    "revision": (type: string),
    "serial": (type: string)
}

```

#### LOGICAL DISK

```
{
    "deviceDiskId": (type: long),
    "driverType": (type: string),
    "fileSystem": (type: string),
    "freeSpace":(type: long),
    "totalSpace": (type: long),
    "name": (type: string),
    "usedSpace": (type: long),
    "volumenName": (type: string)
}

```

#### MEMORY

```
{
    "bank": (type: string),
    "formFactor": (type: string),
    "handler": (type: string),
    "id": (type: int),
    "manufacturer": (type: string),
    "model": (type: string),
    "name": (type: string),
    "serial": (type: string),
    "size": (type: long),
    "speed": (type: int),
    "type": (type: string)
}
```

#### SOFTWARE: Application, Updates

```
 {
      "date": (type: date),
      "deviceId": (type: int),
      "id": (type: int),
      "manufacturer": (type: string),
      "name": (type: string),
      "type": (type: string),
      "uninstallString": (type: string),
      "version": (type: string)
 }
```

Para mayor información consulte las APIs de la plataforma ADM:

+ Device: POST ["/device/list"]
+ Disk: POST ["/device/{id}/disk/list"]
+ Display: POST ["/device/{id}/display/list"]
+ Logical Disk: POST ["/device/{id}/logicaldisk/list"]
+ Memory: POST ["/device/{id}/memory/list"]
+ Software: POST ["/device/{id}/device/{id}/software/list"]