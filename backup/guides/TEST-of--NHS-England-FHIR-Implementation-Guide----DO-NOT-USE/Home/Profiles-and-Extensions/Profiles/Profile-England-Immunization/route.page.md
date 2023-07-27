## `route`

<b>Definition</b><br>

A SNOMED concept ID value from either of the following should be used:
UK “ePrescribing route of administration simple reference set (foundation metadata concept)” (999000051000001100) {{link:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationDosageRoute}}
Or:
UK published reference set “Vaccine route of administration simple reference set” (115231000001104)


```json

 "route": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "78421000",
                "display": "Intramuscular route (qualifier value)"
            }
        ]
    },
```
---