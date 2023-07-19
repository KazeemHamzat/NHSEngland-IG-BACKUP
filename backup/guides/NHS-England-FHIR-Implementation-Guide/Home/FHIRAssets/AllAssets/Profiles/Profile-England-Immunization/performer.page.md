## `performer`

<b>Definition</b><br>

The organisation ODS code of the location where the vaccination event took place with corresponding system of `https://fhir.nhs.uk/Id/ods-organization-code`. For roving teams on home visits or care home visits use the site code of the responsible site e.g. GP practice or dedicated vaccination site. It is strongly recommend the name of the Organisation is present in the display field.

Vaccination professional should be recorded using professional codes, see {{pagelink:Profile-England-Practitioner,text:England-Practitioner}} for details.

```json

"performer":  [
        {
            "actor": {
                "type": "Practitioner",
                "identifier": {
                    "system": "https://fhir.hl7.org.uk/Id/nmc-number",
                    "value": "5566789"
                },
                "display": "HOLDING, Rafferty"
            }
        },
        {
            "actor": {
                "type": "Organization",
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "C4B2A"
                },
                "display": "ELLAND ROAD STADIUM - COVID VACCINATION CENTRE"
            }
        }
    ],
```
---