---
title: Dispositivos ADM (ClassDevice)
chapter: "integracion_serviceNow"
---
*[Volver](../ServiceNow/01_configuracion.html)*  

Este campo representa a los dispositivos descubiertos por ADM

  ```json
{
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
    "mapper": [
    ],
    "dataReference": [
    ],
    "classMapper": [
    ],
    "classCMDB": [
    ]
  }
```

* Sus propiedades 
    +	Fields: Lista de las propiedades que tienen los dispositivos [ver más](../ServiceNow/ClassDevice/README.html)
    +	Name: Nombre del dispositivo

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