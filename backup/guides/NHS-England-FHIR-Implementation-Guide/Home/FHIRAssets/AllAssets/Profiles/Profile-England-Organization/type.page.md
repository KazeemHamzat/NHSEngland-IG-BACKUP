## `type`

<b>Definition:</b>

The Organisation types **MUST** be present and comes from the valueSet.

`type` will also include details on when these roles applied, the current status and a boolean to indicate the Organisations primary role. These extensions are for API's produced by NHS Digital one, the are not expected to be present in resources created by NHS providers or suppliers.

```json
"type":  [
        {
            "extension":  [
                {
                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-ODS-Organization-Role",
                    "extension":  [
                        {
                            "url": "primaryRole",
                            "valueBoolean": true
                        },
                        {
                            "url": "status",
                            "valueString": "Active"
                        }
                    ]
                },
                {
                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-ODS-Organization-Role-ActivePeriod",
                    "extension":  [
                        {
                            "url": "activePeriod",
                            "valuePeriod": {
                                "start": "2020-04-01"
                            }
                        },
                        {
                            "url": "dateType",
                            "valueString": "Operational"
                        }
                    ]
                }
            ],
            "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/organisation-role",
                    "code": "198",
                    "display": "NHS TRUST SITE"
                }
            ]
        }
    ],
```

---

