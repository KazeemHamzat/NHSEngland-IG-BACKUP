## `subject`

<b>Definition:</b><br>

A reference to the patient via a traced NHS Number is required, an untraced NHS Number MUST NOT be used. This can be sent in two ways, first option is via a identifier reference. Only the NHS Number:

```json
"subject": {
    "type": "Patient",
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "2300992742"
    }
}
```
Second option uses a FHIR Patient resource to convey the NHS Number.
The reference in the MedicationDispesnse is now a resource reference.
```json

 "subject": {
                    "type": "Patient",
                    "reference": "urn:uuid:bde9eba6-079f-4210-8108-6ea8db58de8c",
                    "display": "Miss Bernie Kanfeld"
                }

```

The NHS Number has moved to the Patient resource alongside other patient identifiers such as MRN. E.g.

```json
"fullUrl": "urn:uuid:bde9eba6-079f-4210-8108-6ea8db58de8c",
"resource": {
                "resourceType": "Patient",
                "identifier": [
                    {
                        "extension": [
                            {
                                "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NHSNumberVerificationStatus",
                                "valueCodeableConcept": {
                                    "coding": [
                                        {
                                            "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-NHSNumberVerificationStatus",
                                            "code": "01",
                                            "display": "Number present and verified"
                                        }
                                    ]
                                }
                            }
                        ],
                        "system": "https://fhir.nhs.uk/Id/nhs-number",
                        "value": "9876543210"
                    },
                    {
                        "system": "https://fhir.leedsth.nhs.uk/Id/pas-number",
                        "value": "ABC8650149"
                    },
                    {
                        "system": "https://fhir.leedsth.nhs.uk/Id/PPMIdentifier",
                        "value": "1"
                    }
                ],
               ... other elements removed from example.
            }
```

It is anticipated that hospital pharmacies will prefer the later option for compatibility with other systems. Community pharmacies are anticipated to prefer the former option.

---