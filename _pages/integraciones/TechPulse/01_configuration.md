---
title: Configuración
chapter: "integracion_techPulse"
---

La integración entre la plataforma **Aranda Service Desk V8 (ASDK)** y **HP TechPulse**, se realiza mediante la configuración de un archivo en formato JSON. Se basa en el siguiente modelo conceptual:

 ![]({{ site.baseurl }}/assets/images/tech_pulse/integration_techpulse.jpg)  


Donde:
+	**subtypes:** Corresponde al sub-tipo del incidente. [ver más](../TechPulse/02_subtypes_component.html)
+	**filter:** Representa un filtro de búsqueda de incidentes para su respectivo cargue en la plataforma de **Aranda Service Desk V8 (ASDK)** desde **HP TechPulse**.

+	**case:** Corresponde a la informacion del tipo de caso que creara en **Aranda Service Desk V8 (ASDK)**. [ver más](../TechPulse/03_informacion_caso_asdk.html)
+	**tenantIds:** Representa los identificadores de usuarios, empresas y dispositivos unicos gestionados por **HP TechPulse**, que se encuentran relacionados con el incidente. [ver más](../TechPulse/04_tenant_techpulse.html)
+	**uniqueTenant:** Representa TenantId unico relacionado a los incidentes de un tipo. [ver más](../TechPulse/04_tenant_techpulse.html)
