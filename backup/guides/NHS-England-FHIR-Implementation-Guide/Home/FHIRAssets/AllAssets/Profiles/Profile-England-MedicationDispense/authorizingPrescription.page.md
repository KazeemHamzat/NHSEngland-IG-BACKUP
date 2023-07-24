## `authorizingPrescription`

<b>Definition:</b><br>

A reference to the MedicationRequest.

```json
"authorizingPrescription": [
    {
        "reference": "#m1"
    }
]

```
When a MedicationDispesne is sent in a FHIR Message bundle, which is the case with EPS NextGen dispense-notifications, a contained MedicationRequest is required.

This MedicationRequest MUST follow the rules in England-MedicationRequest and it is strongly recommended to reuse the MedicationRequest received when the prescription was downloaded.

For example:

```json
{
                "resourceType": "MedicationDispense",
                "contained":  [
                    {
                        "resourceType": "MedicationRequest",
                        "id": "m1",
                        "identifier":  [
                            {
                                "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                                "value": "299c610b-f4f1-4eac-a7d7-4fb6b0556e11"
                            }
                        ],
                        "status": "active",
                        "intent": "order",
                        "medicationCodeableConcept": {
                            "coding":  [
                                {
                                    "system": "http://snomed.info/sct",
                                    "code": "39720311000001101",
                                    "display": "Paracetamol 500mg soluble tablets"
                                }
                            ]
                        },
                        "subject": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/nhs-number",
                                "value": "9876543210"
                            }
                        },
                        "groupIdentifier": {
                            "extension":  [
                                {
                                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-DMPrescriptionId",
                                    "valueIdentifier": {
                                        "system": "https://fhir.nhs.uk/Id/prescription",
                                        "value": "b2fc79f0-2793-4736-9b2d-0976c21e73a5"
                                    }
                                }
                            ],
                            "system": "https://fhir.nhs.uk/Id/prescription-order-number",
                            "value": "82D996-C81010-11DB12"
                        },
                        "dispenseRequest": {
                            "quantity": {
                                "value": 100,
                                "unit": "tablet",
                                "system": "http://snomed.info/sct",
                                "code": "732936001"
                            }
                        },
                        "substitution": {
                            "allowedBoolean": false
                        }
                    }
                ],
                "authorizingPrescription":  [
                    {
                        "reference": "#m1"
                    }
                ],
}
```

This is based on a MedicationRequest in this implementation guide. The uuid resource references are not permitted and must be replaced with identifier references. E.g. in this section from the $release

```json
      "subject": {
            "reference": "urn:uuid:78d3c2eb-009e-4ec8-a358-b042954aa9b2"
        },
        "authoredOn": "2020-12-21T18:15:29+00:00",
        "requester": {
            "reference": "urn:uuid:56166769-c1c4-4d07-afa8-132b5dfca666"
        },
The requester reference can be removed and the subject reference changed to use the Patient's NHSNumber e.g.

        "subject": {
            "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9876543210"
        }
    }
```

---


