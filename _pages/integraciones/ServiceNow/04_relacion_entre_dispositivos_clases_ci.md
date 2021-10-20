---
title: Relación entre dispositivos y clases CI (ClassMapper)
chapter: "integracion_serviceNow"
---
*[Volver](../ServiceNow/01_configuracion.html)*  

La relación entre los dispositivos descubiertos por ADM y las clases CI de ServiceNow se crea en la entidad “classMapper”.

```json
{
    "classMapper": [
      {
        "classDevice": [

        ],
        "classCMDB": ""
      }
    ],
    "mapper": [
    ],
    "dataReference": [
    ],
    "classDevice": [
    ],
    "classCMDB": [
    ]
  }
```


 

Donde encontramos las siguientes propiedades:

+	ClassDevice: Lista de dispositivos descubiertos por ADM. 

    +	Application.
    +	Updates.
    +	Laptop.
    +	Desktop.
    +	Router.
    +	Switch.
    +	Server.
    +	Unknown.
    +	Printer.
    +	OperatingSystem.
    +	None.
    +	Disk.
    +	LogicalDisk.
    +	Memory. 

+ classCMDB: Nombre de la propiedad de la clase ServiceNow.

La relación uno a muchos (1:n) se crea porque una clase CI puede mapear muchos dispositivos  como es el caso de la clase “cmdb_ci_computer”, sirve para mapear los dispositivos de “Laptop” y “Desktop”.