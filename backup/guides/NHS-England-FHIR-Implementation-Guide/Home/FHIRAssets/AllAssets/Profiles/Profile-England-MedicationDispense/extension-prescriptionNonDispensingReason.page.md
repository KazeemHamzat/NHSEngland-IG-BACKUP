## `extension:prescriptionNonDispensingReason`

<b>Definition:</b><br>

This is the reason a complete prescription was not dispensed, it is not the status of the individual line items, which is contained in MedicationDispense.statusReason.

```json
"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-DMPrescriptionNonDispensingReason",
        "valueCoding": {
            "system": "https://fhir.nhs.uk/CodeSystem/England-MedicationDispenseStatusReason",
            "code": "0002",
            "display": "Clinically unsuitable"
        }
    }
]
```

---