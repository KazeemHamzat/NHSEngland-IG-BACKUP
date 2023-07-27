## `dosageInstruction`

<b>Definition:</b><br>

At present only the text element MUST be provided. It is recommended the guidance in FHIR Dose Syntax Implementation Guidance is followed.

Note the structure of this section is similar as the England-MedicationRequest from the prescription-order.

```json
"dosageInstruction": [
    {
        "text": "4 times a day for 7 days",
        "timing": {
            "repeat": {
                "boundsDuration": {
                    "value": 7,
                    "unit": "d"
                },
                "frequency": 4,
                "period": 1,
                "periodUnit": "d"
            }
        },
        "doseAndRate": [
            {
                "doseQuantity": {
                    "value": 1,
                    "unit": "capsule",
                    "system": "http://snomed.info/sct",
                    "code": "3316911000001105"
                }
            }
        ]
    }
]
```

---