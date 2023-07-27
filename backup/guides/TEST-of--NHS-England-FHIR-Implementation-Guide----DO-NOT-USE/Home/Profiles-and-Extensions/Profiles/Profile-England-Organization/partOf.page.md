## `partOf`

<b>Definition:</b>

Recommended mandatory for primary care organisations.

```json
    "telecom":  [
        {
            "system": "fax",
            "value": "0113 242 6496",
            "use": "work"
        },
        {
            "system": "phone",
            "value": "0113 243 3144",
            "use": "work"
        }
    ],
    "address":  [
        {
            "line":  [
                "KINGS ROAD"
            ],
            "city": "HARROGATE",
            "postalCode": "HG1 5LA",
            "country": "ENGLAND"
        }
    ],
    "partOf": {
        "reference": "https://directory.spineservices.nhs.uk/R4/Organization/RR805",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RR8"
        }
    }
```