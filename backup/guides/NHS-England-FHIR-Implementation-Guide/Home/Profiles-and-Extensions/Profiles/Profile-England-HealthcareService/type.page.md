## `type`

<b>Definition:</b>

Type **SHOULD** be populated.

```json
"type":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/DoS-ClinicType",
                    "code": "PHARMACY",
                    "display": "Pharmacy"
                }
            ]
        }
    ],

```

or 

```json
"type": [
        {
            "coding": [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/eRS-AppointmentType",
                    "code": "DAY_CASE",
                }
            ]
        }
    ],
```

---

