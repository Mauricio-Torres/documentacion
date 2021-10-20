---
title: FIELDS
link: "integraciones/ServiceNow/DataReference"
---
*[Volver](../03_datos_referenciados.html)*  
La propiedad más importante de “dataReference” es “fields” donde asignamos el valor que tendrá la propiedad de la clase de ServiceNow, este valor también esta relacionado con los diferentes dispositivos descubiertos por ADM, 


```json
{
    "dataReference": [
      {
        "name": "",
        "fields": [
          {
            "value": "os",
            "fieldCMDB": "element",
            "classDevice": [
              "Laptop",
              "Desktop"
            ]
          }
        ]
      }
    ]
  }
```
+	ClassDevice: Lista de dispositivos descubiertos por ADM. 

    + Application.
    + Updates.
    + Laptop.
    + Desktop.
    + Router.
    + Switch.
    + Server.
    + Unknown.
    + Printer.
    + OperatingSystem.
    + None.
    + Disk.
    + LogicalDisk.
    + Memory.

+	FieldCMDB: Nombre de la propiedad de la clase ServiceNow.
+	Value: Valor que tendrá la propiedad de la clase ServiceNow. Los tipos de unidad soportados por este campo son: 

    +	int,
    +	long,
    +	float,
    +	decimal,
    +	boolean,
    +	date,
    +	string
    +	array

El tipo array en ServiceNow son considerados como una cadena de “strings” separados por ‘,’. Por esta razón tenga en cuenta que al ingresar un “array” debe ingresarlo de la siguiente forma **[ valores ]** 

Ejm:

- Array numérico: [3, 5. 6].

- Array string: ["valor 1", "valor 2"].
