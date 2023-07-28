## `dispenseRequest.performer.extension`

<b>Definition</b><br>

Details of the dispenser who is actioning the MedicationRequest.

<br>

```json
       "dispenseRequest": { 
                    "performer": {
                        "extension":  [
                            {
                                "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-DispensingPerformer",
                                "valueReference": {
                                    "reference": "urn:uuid:25f3dd9f-5838-44a7-930e-c78ae3ecadd6",
                                    "display": "LOTTIE POTTS"
                                }
                            }
                        ],
                        "identifier": {
                            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                            "value": "VNE51"
                        },
                        "display": "The Simple Pharmacy"
                    }
                },
```

---