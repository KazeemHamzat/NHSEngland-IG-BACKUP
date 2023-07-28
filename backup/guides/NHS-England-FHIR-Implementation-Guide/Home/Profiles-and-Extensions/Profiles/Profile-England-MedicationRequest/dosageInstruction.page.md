## `dosageInstruction`

<b>Definition</b><br>

The content of the `dosageInstruction` should follow guidance in [Digital Medicines Dosage](https://simplifier.net/guide/ukcoreimplementationguideformedicines/ElementDosage).


`dosageInstruction.text` **MUST** be supplied and is a human readable version of the structured dose as would be printed on a paper prescription. The use of a generic default value, for example “Use as directed”, if a value is not entered, is not acceptable from a clinical perspective. The user must be asked to select a dosage instruction from a pick list, type by hand or have the system populate with a valid and clinically safe dosage instruction relevant to the prescribed medication or clinical circumstances.

As per BNF guidelines, the dosage must be presented to the user without abbreviation although it may be entered and stored within the PMR in an abbreviated form. Within HL7 messaging, the dosage instruction must be represented without abbreviation.

<br>

```json
"dosageInstruction": [
   {
        "text": "Inject 10 milligram, once a week, Subcutaneous route, for 10 weeks",
        "timing": {
            "repeat": {
                "boundsDuration": {
                    "value": 10,
                    "unit": "week",
                     "system": "http://unitsofmeasure.org",
                     "code": "wk"
                },
                 "frequency": 1,
                 "period": 1,
                "periodUnit": "wk"
             }
        },
        "route": {
            "coding": [
                {
                    "system": "http://snomed.info/sct",
                    "code": "34206005",
                    "display": "Subcutaneous route"
                }
            ]
        },
        "method": {
            "coding": [
                {
                    "system": "http://snomed.info/sct",
                    "code": "422145002",
                    "display": "Inject"
                }
            ]
        },
        "doseAndRate": [
            {
                "doseQuantity": {
                    "value": 10,
                    "unit": "milligram",
                    "system": "http://unitsofmeasure.org",
                    "code": "mg"
                }
            }
        ]
    }
]
```

---
