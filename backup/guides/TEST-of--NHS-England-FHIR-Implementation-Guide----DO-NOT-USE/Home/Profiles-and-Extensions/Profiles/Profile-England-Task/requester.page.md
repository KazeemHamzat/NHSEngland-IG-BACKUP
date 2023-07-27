## `requester`

<b>Definition</b><br>

Who created the Request or the Event. In NHSDigital API's this **SHOULD** always be a PractitionerRole role reference.

```json
 "requester": {
        "reference": "#requester"
    },
```

This will reference a `contained` PractitionerRole (note: this resource only contains limited user metadata such as ODS Code, professional code and SDS User Profile Id). This resource should not hold data which is held in SDS, only enough information to identify the SDS Entry,

```json
{
    "resourceType": "Task",
    "id": "bd1ca5c4-ff49-4f2a-9db4-f5dda0112084",
    "meta": {
        "lastUpdated": "2016-07-11T11:07:22+00:00"
    },
    "contained": [
        {
            "resourceType": "PractitionerRole",
            "id": "requester",
            "practitioner": {
                "identifier": {
                    "system": "https://fhir.hl7.org.uk/Id/gmp-number",
                    "value": "G8123456"
                },
                "display": "DR AA BHATIA"
            },
            "organization": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "C81007"
                },
                "display": "VERNON STREET MEDICAL CTR"
            },
            "telecom": [
                {
                    "system": "phone",
                    "use": "work",
                    "value": "01234567890"
                }
            ]
        }
    ],
```

---