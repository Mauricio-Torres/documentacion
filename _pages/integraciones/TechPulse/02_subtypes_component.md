---
title: Sub Tipos
chapter: "integracion_techPulse"
---

HP TechPulse clasifica los incidentes en tipos y sub – tipos, dentro de los subtipos tenemos:

 ![]({{ site.baseurl }}/assets/images/tech_pulse/subtype_list_techpulse.png)  


Las API de HP TechPulse reconoce los sub tipos como se muestran en la columna  **"subtypes"**, estos valores estarán relacionados directamente con el tipo de caso al que serán equivalentes en ASDK.

Para realizar la integración escribimos estos valores de la siguiente forma:



```json
{
   "mappers":[
      {
         "id":"",
         "subtypes":[
            "COMPANY_WIDE_BIOS_OUTOFDATE",
            "BATTERY_NEEDS_ATTENTION",
            "BATTERY_NOT_DETECTED",
            "BATTERY_RECALL",
            "PERF_CPU",
            "COMPANY_WIDE_OS_BSOD",
            "COMPANY_WIDE_CRITICAL_DRIVER_OUTOFDATE",
            "HDD",
            "HDD_PREDICTIVE_FAILURE",
            "HDD_SMART_EVENT_FAIL",
            "HDD_STORAGE_FULL",
            "HP_TECHPULSE_INCIDENT_INTEGRATION",
            "HEARTBEAT_FAILURE",
            "LICENSING",
            "MEMORY",
            "PERF_MEMORY",
            "OS_BSOD",
            "OS_CRASH",
            "SYSTEM_ERROR_THERMAL",
            "UNKNOWN"
         ],
         "filter":"",
         "case":{
            "caseType": 0,
            "project":0,
            "service":0,
            "category":0,
            "group":0,
            "registryType":0,
            "state":[
               {
                  "name":"",
                  "value":0
               }               
            ],
            "sla":,
            "company":,
            "urgency": [
               {
                  "name": "",
                  "value": 0
               }
            ]
         }
      }
   ],
   "tenantIds":[
      ""
   ],
   "uniqueTenant":""
}

```