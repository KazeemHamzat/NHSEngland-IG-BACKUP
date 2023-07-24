## `extension:prescriptionStatus`

<b>Definition:</b><br>

This is the overall status of the prescription-order, it is not the status of the individual prescription item. This is a code from {{pagelink:CodeSystem-England-EPSTaskBusinessStatus}}, all prescription status reasons in a dispense-notification FHIR Message Bundle must be the same.


```json
"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-EPSTaskBusinessStatus",
        "valueCoding": {
            "system": "https://fhir.nhs.uk/CodeSystem/England-EPSTaskBusinessStatus",
            "code": "0003",
            "display": "With Dispenser - Active"
        }
    }
]
```

---