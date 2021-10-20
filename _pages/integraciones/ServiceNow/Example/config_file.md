---
title: Resultado final
link: "example"
---

*[Volver](../08_ejemplo.html)*  

Como resultado final y mapeando todas las clases de ServiceNow que relacionan los dispositivos descubiertos por ADM y la CMDB de ServiceNow obtenemos el siguiente resultado

```json
{
  "mapper": [
    {
      "name": "Partition-Disk-Reference",
      "fields": [
        {
          "fieldDevice": "idDevice",
          "fieldCMDB": "computer"
        },
        {
          "fieldDevice": "idDisk",
          "fieldCMDB": "disk"
        }
      ]
    },
    {
      "name": "Partition-Disk-Reference-Mapper",
      "fields": [
        {
          "fieldDevice": "name",
          "fieldCMDB": "name"
        },
        {
          "fieldDevice": "freeSpace",
          "fieldCMDB": "start_offset"
        },
        {
          "fieldDevice": "usedSpace",
          "fieldCMDB": "end_offset"
        }
      ]
    },
    {
      "name": "ApplicationSoftwareReferenced",
      "fields": [
        {
          "fieldDevice": "version",
          "fieldCMDB": "version"
        },
        {
          "fieldDevice": "name",
          "fieldCMDB": "name"
        },
        {
          "fieldDevice": "date",
          "fieldCMDB": "install_date"
        }
      ]
    },
    {
      "name": "ManufacturerCompanyAppSoftwareReference",
      "fields": [
        {
          "fieldDevice": "manufacturer",
          "fieldCMDB": "name"
        }
      ]
    },
    {
      "name": "HardwareProductModelReference",
      "fields": [
        {
          "fieldDevice": "model",
          "fieldCMDB": "name"
        },
        {
          "fieldDevice": "model",
          "fieldCMDB": "short_description"
        }
      ]
    },
    {
      "name": "OperatingSystemReferenced",
      "fields": [
        {
          "fieldDevice": "operatingSystem",
          "fieldCMDB": "os"
        }
      ]
    },
    {
      "name": "Computer-Disk-Reference",
      "fields": [
        {
          "fieldDevice": "id",
          "fieldCMDB": "computer"
        }
      ]
    },
    {
      "name": "MemoryReference",
      "fields": [
        {
          "fieldDevice": "features",
          "fieldCMDB": "short_description"
        },
        {
          "fieldDevice": "bank",
          "fieldCMDB": "device_id"
        },
        {
          "fieldDevice": "busType",
          "fieldCMDB": "device_interface"
        },
        {
          "fieldDevice": "size",
          "fieldCMDB": "disk_space"
        },
        {
          "fieldDevice": "serial",
          "fieldCMDB": "serial_number"
        },
        {
          "fieldDevice": "name",
          "fieldCMDB": "name"
        }
      ]
    },
    {
      "name": "DiskReference",
      "fields": [
        {
          "fieldDevice": "features",
          "fieldCMDB": "short_description"
        },
        {
          "fieldDevice": "pnpDeviceId",
          "fieldCMDB": "device_id"
        },
        {
          "fieldDevice": "busType",
          "fieldCMDB": "device_interface"
        },
        {
          "fieldDevice": "size",
          "fieldCMDB": "size"
        },
        {
          "fieldDevice": "serial",
          "fieldCMDB": "serial_number"
        },
        {
          "fieldDevice": "pnpDeviceId",
          "fieldCMDB": "name"
        },
        {
          "fieldDevice": "freeSpace",
          "fieldCMDB": "free_space"
        },
        {
          "fieldDevice": "size",
          "fieldCMDB": "disk_space"
        }
      ]
    },
    {
      "name": "UserDeviceReference",
      "fields": [
        {
          "fieldDevice": "responsibleUserName",
          "fieldCMDB": "first_name"
        },
        {
          "fieldDevice": "responsibleUserName",
          "fieldCMDB": "last_name"
        },
        {
          "fieldDevice": "userName",
          "fieldCMDB": "user_name"
        },
        {
          "fieldDevice": "responsibleUserEmail",
          "fieldCMDB": "email"
        }
      ]
    },
    {
      "name": "CompanyManufacturerReference",
      "fields": [
        {
          "fieldDevice": "manufacturer",
          "fieldCMDB": "name"
        }
      ]
    },
    {
      "name": "DeviceComputerReferenceNetwork",
      "fields": [
        {
          "fieldDevice": "domain",
          "fieldCMDB": "dns_domain"
        },
        {
          "fieldDevice": "ipRegistred",
          "fieldCMDB": "ip_address"
        }
      ]
    },
    {
      "name": "DeviceComputerReference",
      "fields": [
        {
          "fieldDevice": "operatingSystemVersion",
          "fieldCMDB": "os_version"
        },
        {
          "fieldDevice": "name",
          "fieldCMDB": "name"
        },
        {
          "fieldDevice": "description",
          "fieldCMDB": "short_description"
        },
        {
          "fieldDevice": "serial",
          "fieldCMDB": "serial_number"
        },
        {
          "fieldDevice": "creationDate",
          "fieldCMDB": "sys_created_on"
        },
        {
          "fieldDevice": "id",
          "fieldCMDB": "object_id"
        },
        {
          "fieldDevice": "discovery_source",
          "fieldCMDB": "discovery_source"
        },
        {
          "fieldDevice": "totalRam",
          "fieldCMDB": "ram"
        },
        {
          "fieldDevice": "cpuCore",
          "fieldCMDB": "cpu_count"
        },
        {
          "fieldDevice": "cpuLogic",
          "fieldCMDB": "cpu_core_count"
        },
        {
          "fieldDevice": "diskTotal",
          "fieldCMDB": "disk_space"
        }

      ]
    },
    {
      "name": "PublisherCompanyReference",
      "fields": [
        {
          "fieldDevice": "manufacturer",
          "fieldCMDB": "name"
        }
      ]
    }
  ],
  "dataReference": [
    {
      "name": "OperatingSystemReferenced",
      "fields": [
        {
          "value": "os",
          "fieldCMDB": "lement",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        },
        {
          "value": "cmdb_ci_computer",
          "fieldCMDB": "name",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        }
      ]
    },
    {
      "name": "StorageTypeSysChoice",
      "fields": [
        {
          "value": "Disk",
          "fieldCMDB": "storage_type",
          "classDevice": [
            "Disk"
          ]
        }
      ]
    },
    {
      "name": "StorageTypeSysChoice",
      "fields": [
        {
          "value": "RAM",
          "fieldCMDB": "storage_type",
          "classDevice": [
            "Memory"
          ]
        }
      ]
    },
    {
      "name": "DiscoverySourceReferenced",
      "fields": [
        {
          "value": "Aranda Software",
          "fieldCMDB": "discovery_source",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        },
        {
          "value": "os",
          "fieldCMDB": "lement",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        },
        {
          "value": "cmdb_ci_computer",
          "fieldCMDB": "name",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        }
      ]
    },
    {
      "name": "CompanyManufacturerReference",
      "fields": [
        {
          "value": "false",
          "fieldCMDB": "manufacturer",
          "classDevice": [
            "Laptop",
            "Desktop",
            "Router",
            "Switch",
            "Server",
            "Application",
            "Software",
            "Updates"
          ]
        },
        {
          "value": "false",
          "fieldCMDB": "vendor",
          "classDevice": [
            "Laptop",
            "Desktop",
            "Router",
            "Switch",
            "Server"
          ]
        }
      ]
    },

    {
      "name": "ManufacturerCompanyAppSoftwareReference",
      "fields": [
        {
          "value": "false",
          "fieldCMDB": "manufacturer",
          "classDevice": [
            "Application",
            "Software",
            "Updates"
          ]
        },
        {
          "value": "false",
          "fieldCMDB": "vendor",
          "classDevice": [
            "Application",
            "Software",
            "Updates"
          ]
        }
      ]
    },

    {
      "name": "TypeSoftwareReference",
      "fields": [
        {
          "value": "Application Software",
          "fieldCMDB": "sys_class_name",
          "classDevice": [
            "Application",
            "Updates"
          ]
        }
      ]
    },
    {
      "name": "CompanyOwnerReference",
      "fields": [
        {
          "value": "Aranda Software",
          "fieldCMDB": "name",
          "classDevice": [
            "Laptop",
            "Desktop",
            "Router",
            "Switch",
            "Server",
            "Application",
            "Software",
            "Updates"
          ]
        },
        {
          "value": "false",
          "fieldCMDB": "manufacturer",
          "classDevice": [
            "Laptop",
            "Desktop",
            "Router",
            "Switch",
            "Server",
            "Application",
            "Software",
            "Updates"
          ]
        },
        {
          "value": "false",
          "fieldCMDB": "vendor",
          "classDevice": [
            "Laptop",
            "Desktop",
            "Router",
            "Switch",
            "Server",
            "Application",
            "Software",
            "Updates"
          ]
        }
      ]
    },
    {
      "name": "HardwareCategoryReference",
      "fields": [
        {
          "value": "cmdb_ci_computer",
          "fieldCMDB": "cmdb_ci_class",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        }
      ]
    },
    {
      "name": "HardwareCategoryReference",
      "fields": [
        {
          "value": "cmdb_ci_server",
          "fieldCMDB": "cmdb_ci_class",
          "classDevice": [
            "Laptop",
            "Desktop"
          ]
        }
      ]
    },
    {
      "name": "HardwareCategoryReference",
      "fields": [
        {
          "value": "cmdb_ci_server",
          "fieldCMDB": "cmdb_ci_class",
          "classDevice": [
            "Server"
          ]
        }
      ]
    },
    {
      "name": "HardwareCategoryReference",
      "fields": [
        {
          "value": "",
          "fieldCMDB": "cmdb_ci_class",
          "classDevice": [
            "Router",
            "Switch"
          ]
        }
      ]
    }
  ],
  "classMapper": [
    {
      "classDevice": [
        "Desktop",
        "Laptop"
      ],
      "classCMDB": "cmdb_ci_computer"
    },
    {
      "classDevice": [
        "Disk"
      ],
      "classCMDB": "disk"
    },
    {
      "classDevice": [
        "Memory"
      ],
      "classCMDB": "memory"
    },
    {
      "classDevice": [
        "LogicalDisk"
      ],
      "classCMDB": "cmdb_ci_disk_partition"
    },
    {
      "classDevice": [
        "Application",
        "Updates"
      ],
      "classCMDB": "cmdb_ci_application_software"
    }
  ],
  "classDevice": [
    {
      "name": "Desktop",
      "fields": [
        {
          "type": "string",
          "name": "name"
        }
      ]
    },
    {
      "name": "Laptop",
      "fields": [
        {
          "type": "string",
          "name": "name"
        }
      ]
    },
    {
      "name": "Application",
      "fields": [
        {
          "type": "string",
          "name": "name"
        }
      ]
    },
    {
      "name": "Updates",
      "fields": [
        {
          "type": "string",
          "name": "name"
        }
      ]
    },
    {
      "name": "Disk",
      "fields": [
        {
          "type": "string",
          "name": "name"
        }
      ]
    }
  ],
  "classCMDB": [
    {
      "searchBy": [
        "name",
        "disk",
        "computer"
      ],
      "name": "cmdb_ci_disk_partition",
      "fields": [
        {
          "type": "string",
          "name": "discovery_source",
          "mappingType": "SysChoice",
          "mappingName": "Partition-Disk-Reference",
          "isRequired": false,
          "classReference": "sys_choice"
        },

        {
          "type": "string",
          "name": "disk",
          "mappingType": "Reference",
          "mappingName": "Partition-Disk-Reference",
          "isRequired": false,
          "classReference": "cmdb_ci_disk"
        },
        {
          "type": "string",
          "name": "computer",
          "mappingType": "Reference",
          "mappingName": "Partition-Disk-Reference",
          "isRequired": false,
          "classReference": "cmdb_ci_computer"
        },

        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": "Partition-Disk-Reference-Mapper",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "decimal",
          "name": "start_offset",
          "mappingType": "Mapper",
          "mappingName": "Partition-Disk-Reference-Mapper",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "decimal",
          "name": "end_offset",
          "mappingType": "Mapper",
          "mappingName": "Partition-Disk-Reference-Mapper",
          "isRequired": false,
          "classReference": null
        }

      ]
    },

    {
      "searchBy": [
        "name"
      ],
      "name": "cmdb_ci_application_software",
      "fields": [
        {
          "type": "string",
          "name": "sys_class_name",
          "mappingType": "SysChoice",
          "mappingName": "TypeSoftwareReference",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "install_date",
          "mappingType": "Mapper",
          "mappingName": "ApplicationSoftwareReferenced",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "version",
          "mappingType": "Mapper",
          "mappingName": "ApplicationSoftwareReferenced",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": "ApplicationSoftwareReferenced",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "manufacturer",
          "mappingType": "Reference",
          "mappingName": "ManufacturerCompanyAppSoftwareReference",
          "isRequired": false,
          "classReference": "core_company"
        }
      ]
    },
    {
      "searchBy": [
        "serial_number",
        "device_id",
        "computer"
      ],
      "name": "cmdb_ci_disk",
      "alias": "memory",
      "fields": [
        {
          "type": "string",
          "name": "device_interface",
          "mappingType": "SysChoice",
          "mappingName": "MemoryReference",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "storage_type",
          "mappingType": "SysChoice",
          "mappingName": "StorageTypeSysChoice",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "discovery_source",
          "mappingType": "SysChoice",
          "mappingName": "DiscoverySourceReferenced",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "manufacturer",
          "mappingType": "Reference",
          "mappingName": "CompanyManufacturerReference",
          "isRequired": false,
          "classReference": "core_company"
        },

        {
          "type": "string",
          "name": "model_id",
          "mappingType": "Reference",
          "mappingName": "HardwareProductModelReference",
          "isRequired": false,
          "classReference": "cmdb_hardware_product_model"
        },
        {
          "type": "string",
          "name": "computer",
          "mappingType": "Reference",
          "mappingName": "Computer-Disk-Reference",
          "isRequired": false,
          "classReference": "cmdb_ci_computer"
        },
        {
          "type": "string",
          "name": "device_id",
          "mappingType": "Mapper",
          "mappingName": "MemoryReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": "MemoryReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "short_description",
          "mappingType": "Mapper",
          "mappingName": "MemoryReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "serial_number",
          "mappingType": "Mapper",
          "mappingName": "MemoryReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "disk_space",
          "unit": "GB",
          "mappingType": "Mapper",
          "mappingName": "MemoryReference",
          "isRequired": false,
          "classReference": null
        }
      ]
    },
    {
      "searchBy": [
        "serial_number",
        "device_id",
        "computer"
      ],
      "name": "cmdb_ci_disk",
      "alias": "disk",
      "fields": [
        {
          "type": "string",
          "name": "device_interface",
          "mappingType": "SysChoice",
          "mappingName": "DiskReference",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "storage_type",
          "mappingType": "SysChoice",
          "mappingName": "StorageTypeSysChoice",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "discovery_source",
          "mappingType": "SysChoice",
          "mappingName": "DiscoverySourceReferenced",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "manufacturer",
          "mappingType": "Reference",
          "mappingName": "CompanyManufacturerReference",
          "isRequired": false,
          "classReference": "core_company"
        },
        {
          "type": "string",
          "name": "company",
          "mappingType": "Reference",
          "mappingName": "CompanyOwnerReference",
          "isRequired": false,
          "classReference": "core_company"
        },
        {
          "type": "string",
          "name": "model_id",
          "mappingType": "Reference",
          "mappingName": "HardwareProductModelReference",
          "isRequired": false,
          "classReference": "cmdb_hardware_product_model"
        },
        {
          "type": "string",
          "name": "computer",
          "mappingType": "Reference",
          "mappingName": "Computer-Disk-Reference",
          "isRequired": false,
          "classReference": "cmdb_ci_computer"
        },
        {
          "type": "string",
          "name": "device_id",
          "mappingType": "Mapper",
          "mappingName": "DiskReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": "DiskReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "short_description",
          "mappingType": "Mapper",
          "mappingName": "DiskReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "size",
          "mappingType": "Mapper",
          "mappingName": "DiskReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "serial_number",
          "mappingType": "Mapper",
          "mappingName": "DiskReference",
          "isRequired": false,
          "classReference": null
        },

        {
          "type": "integer",
          "name": "disk_space",
          "unit": "GB",
          "mappingType": "Mapper",
          "mappingName": "DiskReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "free_space",
          "unit": "GB",
          "mappingType": "Mapper",
          "mappingName": "DiskReference",
          "isRequired": false,
          "classReference": null
        }
      ]
    },
    {
      "searchBy": [
        "object_id"
      ],
      "name": "cmdb_ci_computer",
      "fields": [
        {
          "type": "string",
          "name": "os",
          "mappingType": "SysChoice",
          "mappingName": "OperatingSystemReferenced",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "discovery_source",
          "mappingType": "SysChoice",
          "mappingName": "DiscoverySourceReferenced",
          "isRequired": false,
          "classReference": "sys_choice"
        },
        {
          "type": "string",
          "name": "manufacturer",
          "mappingType": "Reference",
          "mappingName": "CompanyManufacturerReference",
          "isRequired": false,
          "classReference": "core_company"
        },
        {
          "type": "string",
          "name": "company",
          "mappingType": "Reference",
          "mappingName": "CompanyOwnerReference",
          "isRequired": false,
          "classReference": "core_company"
        },
        {
          "type": "string",
          "name": "model_id",
          "mappingType": "Reference",
          "mappingName": "HardwareProductModelReference",
          "isRequired": false,
          "classReference": "cmdb_hardware_product_model"
        },
        {
          "type": "string",
          "name": "assigned_to",
          "mappingType": "Reference",
          "mappingName": "UserDeviceReference",
          "isRequired": false,
          "classReference": "sys_user"
        },
        {
          "type": "string",
          "name": "os_version",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "string",
          "name": "short_description",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "disk_space",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "dns_domain",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReferenceNetwork",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "ip_address",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReferenceNetwork",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "sys_created_on",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "sys_created_on",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "unit": "MB",
          "name": "ram",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "unit": "GB",
          "name": "disk_space",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "cpu_count",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "integer",
          "name": "cpu_core_count",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "object_id",
          "mappingType": "Mapper",
          "mappingName": "DeviceComputerReference",
          "isRequired": false,
          "classReference": null
        }
      ]
    },
    {
      "searchBy": [
        "user_name"
      ],
      "name": "sys_user",
      "fields": [
        {
          "type": "string",
          "name": "first_name",
          "mappingType": "Mapper",
          "mappingName": null,
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "string",
          "name": "last_name",
          "mappingType": "Mapper",
          "mappingName": null,
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "string",
          "name": "user_name",
          "mappingType": "Mapper",
          "mappingName": null,
          "isRequired": true,
          "classReference": null
        }
      ]
    },
    {
      "searchBy": [
        "cmdb_ci_class"
      ],
      "name": "cmdb_model_category",
      "fields": [
        {
          "type": "string",
          "name": "cmdb_ci_class",
          "mappingType": "Data",
          "mappingName": null,
          "isRequired": true,
          "classReference": null
        }
      ]
    },
    {
      "searchBy": [
        "name"
      ],
      "name": "core_company",
      "fields": [
        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": null,
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "boolean",
          "name": "manufacturer",
          "mappingType": "Data",
          "mappingName": null,
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "boolean",
          "name": "vendor",
          "mappingType": "Data",
          "mappingName": null,
          "isRequired": false,
          "classReference": null
        }
      ]
    },
    {
      "searchBy": [
        "name",
        "label"
      ],
      "name": "sys_choice",
      "fields": [
        {
          "type": "string",
          "name": "element",
          "mappingType": "Data",
          "mappingName": null,
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "string",
          "name": "name",
          "mappingType": "Data",
          "mappingName": null,
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "string",
          "name": "value",
          "mappingType": "Mapper",
          "mappingName": null,
          "isRequired": false,
          "classReference": null
        },
        {
          "type": "string",
          "name": "label",
          "mappingType": "Mapper",
          "mappingName": null,
          "isRequired": false,
          "classReference": null
        }
      ]
    },
    {
      "searchBy": [
        "name"
      ],
      "name": "cmdb_hardware_product_model",
      "fields": [
        {
          "type": "string",
          "name": "manufacturer",
          "mappingType": "Reference",
          "mappingName": "CompanyManufacturerReference",
          "isRequired": false,
          "classReference": "core_company"
        },
        {
          "type": "array",
          "name": "cmdb_model_category",
          "mappingType": "Reference",
          "mappingName": "HardwareCategoryReference",
          "isRequired": false,
          "classReference": "cmdb_model_category"
        },
        {
          "type": "string",
          "name": "name",
          "mappingType": "Mapper",
          "mappingName": null,
          "isRequired": true,
          "classReference": null
        },
        {
          "type": "string",
          "name": "short_description",
          "mappingType": "Mapper",
          "mappingName": null,
          "isRequired": false,
          "classReference": null
        }
      ]
    }
  ],
  "relationship": [
    {
      "parentClassDevice": "Desktop",
      "childClassDevice": "Application",
      "relationshipType": "Used by::Uses"
    },
    {
      "parentClassDevice": "Laptop",
      "childClassDevice": "Application",
      "relationshipType": "Used by::Uses"
    },
    {
      "parentClassDevice": "Desktop",
      "childClassDevice": "Disk",
      "relationshipType": "Used by::Uses"
    },
    {
      "parentClassDevice": "Laptop",
      "childClassDevice": "Disk",
      "relationshipType": "Used by::Uses"
    },
    {
      "parentClassDevice": "Desktop",
      "childClassDevice": "LogicalDisk",
      "relationshipType": "Used by::Uses"
    },
    {
      "parentClassDevice": "Laptop",
      "childClassDevice": "LogicalDisk",
      "relationshipType": "Used by::Uses"
    }
  ]
}
```