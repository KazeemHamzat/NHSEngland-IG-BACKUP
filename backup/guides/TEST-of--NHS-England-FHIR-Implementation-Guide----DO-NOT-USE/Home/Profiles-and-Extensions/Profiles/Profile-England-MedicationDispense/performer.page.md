## `performer`

<b>Definition:</b><br>

The pharmacist and pharmacy MUST be present and MUST use identifier references. This means FHIR Practitioner, Organization and PractitionerRole resource are not included in the FHIR Message. Professional codes and ODS codes should be used instead. sds-user-role-id is permitted to identify a Practitioner(& Role) but professional codes are preferred to support wider NHS interoperability.

```json
 "performer": [
    {
        "actor": {
            "reference" : "#performer"
        }
    }
]
```
The contained PractitionerRole:

```json
{
    "resourceType": "MedicationDispense",
    "id": "06167339-9337-d030-0366-514a6a46da17",
    "contained": [
        {
                        "resourceType": "PractitionerRole",
                        "id": "performer",
                        "identifier": [
                            {
                                "system": "https://fhir.nhs.uk/Id/sds-role-profile-id",
                                "value": "741555508105"
                            }
                        ],
                        "code": [
                            {
                                "coding": [
                                    {
                                        "system": "https://fhir.nhs.uk/CodeSystem/England-SDSJobRoleCode",
                                        "code": "S0030:G0100:R0620"
                                    }
                                ]
                            }
                        ],
                        "practitioner": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/sds-user-id",
                                "value": "7654321"
                            },
                            "display": "Mr Peter Potion"
                        },
                        "organization": {
                            "reference": "urn:uuid:2bf9f37c-d88b-4f86-ad5f-373c1416e04b"
                        },
                        "telecom": [
                            {
                                "system": "phone",
                                "use": "work",
                                "value": "0532567890"
                            }
                        ]
                   }
    ],
}
```

---
