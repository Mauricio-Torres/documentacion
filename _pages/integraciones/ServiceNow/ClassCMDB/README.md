---
title: Atributos de las clases CI (fields)
link: "integraciones/ServiceNow/ClassCMDB"
---
*[Volver](../06_clases_cmdb_servicenow.html)*  

Los atributos de la clase CMDB son representados en la propiedad “fields” de “ClassCMDB”, estos representan la configuración mínima de los atributos necesario para registrar datos en ServiceNow.

Las propiedades para configurar los atributos de la clase CI son:

```json
{
    "classCMDB": [
      {
        "fields": [
          {
            "unit":"",
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


###	**Type:** 
Representa el tipo de valor que acepta este campo en la CMDB, los tipos pueden ser:

+	integer.
+	decimal.
+	boolean.
+	date.
+	array.
+	string.

###	**Name:**
Representa el nombre del campo en la CMDB de ServiceNow.

###	**Unit:**
Representa el tipo de unidad con la que se representa el atributo de la clase CI, solo es válido para los tipo “integer” o “decimal”.

El tipo de unidad puede ser:

+	B,
+	KB,
+	MB,
+	GB,
+	TB,
+	PB,
+	YB 


 ![]({{ site.baseurl }}/assets/images/service_now/units_class_ci.png)  

###	**MappingType:**
Los atributos de las clases de ServiceNow pueden contener valores que hagan referencia a otra entidad (clase) o su valor puede ser ingresado por el usuario.

Los atributos que hacen relación a otras entidades son designados por ServiceNow como “reference” o su valor se puede obtener de un “select box” como se explica a continuación:


####	Atributos Sys_Choice y Reference

ServiceNow puede relacionar sus clases mediante dos tipos de atributos, de tipo **"reference"** y **"sys_choice"**.

Los atributos de tipo reference se pueden encontrar como se muestra en la imagen:

 ![]({{ site.baseurl }}/assets/images/service_now/Integracion_AtributosReferencia.png)  


Mientras que el valor se pueda seleccionar de un **"select box"**, estamos trabajando con atributos de tipo **"sys_choice"**, los valores contenidos se agregan a la clase **"sys_choice"** y se relacionan con la clase CI


 ![]({{ site.baseurl }}/assets/images/service_now/Integracion_AtributosSysChoice.png)  

	

Para la integración entre ADM y la CMDB de ServiceNow se asigna el campo “mappingType” que tiene en consideración las diferentes formas como se obtendrá el valor del atributo, este campo puede ocupar los siguientes valores:
+	Mapper: El valor del atributo se obtiene directamente del dispositivo, se forma una relación 1:1 entre nombre del atributo y el nombre de la propiedad del dispositivo.
+	Data: El valor del atributo lo ingresa el usuario como un valor estándar para todos los dispositivos que se integren con ServiceNow, el valor se registrara en la propiedad **DataReference** [ver mas](../03_datos_referenciados.html)*.
+	SysChoice: Este valor solo es válido para atributos con un “select box”, en caso de no existir en la CMDB de ServiceNow lo registra.
+	Reference: Este valor solo es válido para atributos de tipo “Reference”, en caso de no existir en la CMDB de ServiceNow lo registra
+	None: Funciona igual que un SysChoice o un Reference, con la diferencia que si no existe el valor no sera añadido a la CMDB de ServiceNow.

### **MappingName:** 
Representa el nombre hacia la referencia de 'mapper' o ‘dataReference'. 

 ![]({{ site.baseurl }}/assets/images/service_now/Integracion_MappingName.png)  


### **IsRequired:** 
Representa si este atributo es requerido en la CMDB de ServiceNow, si el atributo es requerido y no se encuentra el atributo ya sea mapeándolo del dispositivo o asignándolo por el usuario en ‘dataReference’ no se creara y el valor será ‘null’
### **ClassReference:**
Representa el nombre de la clase a la que se referencia cuando el 'MappingType' es 'Reference'.