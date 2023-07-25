## `patient`

<b>Definition</b><br>

A traced NHS Number **SHOULD** be provided and when applicable a resource reference to the Patient resource.

```json
"patient": {
                    "reference": "urn:uuid:edea022a-2d81-11eb-adc1-0242ac120002",
                    "type": "Patient",
                    "identifier": {
                        "system": "https://fhir.nhs.uk/Id/nhs-number",
                        "value": "9912003888"
                    }
                },
```

---