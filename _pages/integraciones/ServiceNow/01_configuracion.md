---
title: Configuración 
chapter: "integracion_serviceNow"
---
La integración entre la plataforma **Aranda Device Management (ADM)** y la **CMDB de ServiceNow**, se realiza mediante la configuración de un archivo en formato JSON. Se basa en el siguiente modelo conceptual:


 ![]({{ site.baseurl }}/assets/images/service_now/Integration-ServiceNow-ADM.png)  

Donde:
+	**Mapper:** Representa la relación que se formara entre los campos del dispositivo de ADM y los campos de la clase CI de ServiceNow. [ver más](../ServiceNow/02_relacion_entre_servicenow_adm.html)
+	**DataReference:** Representa los datos que se asignaran a las clases Ci de ServiceNow, estos datos no se encuentran en las API de ADM y se requieren para crear los registros.[ver más](../ServiceNow/03_datos_referenciados.html)
+	**ClassMapper:** Representa La relación que se formara entre los dispositivos registrados en ADM y las clases CI de la CMDB de ServiceNow. [ver más](../ServiceNow/04_relacion_entre_dispositivos_clases_ci.html)
+	**ClassDevice:** Representa los dispositivos registrados (Descubiertos) en ADM. [ver más](../ServiceNow/05_dispositivos_adm.html)
+	**ClassCMDB:** Representa las clases CI de la CMDB ServiceNow. [ver más](../ServiceNow/06_clases_cmdb_servicenow.html)
+	**Relationship:** Representa la relación que existen entre las clases CI de la CMDB ServiceNow. [ver más](../ServiceNow/07_relacion_entre_clases_ci.html)

