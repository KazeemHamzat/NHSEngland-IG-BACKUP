## `basedOn`

<b>Definition</b><br>

This MUST be populated for `continuous-repeat-dispensing` issues where intent=`reflex-order`, i.e. the issues sent from EPS to pharmacists. It is recommended this is populated for `continuous` issues and this should reference the original order.

Example for a `reflex-order` (continuous-repeat-dispensing):

<br>

```json 

"basedOn": [
        {
            "extension": [
                {
                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation",
                    "extension": [
                        {
                            "url": "numberOfRepeatsAllowed",
                            "valueInteger": 6
                        }
                    ]
                }
            ],
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                "value": "A7B86F8D-1D59-FC28-E050-D20AE3A215F0"
            }
        }
    ]

```

Example for a ` instance - order ` (continuous). Note this references an example MedicationRequest from GP Connect:

<br>

``` json

 "basedOn": [
        {
            "extension": [
                {
                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation",
                    "extension": [
                        {
                            "url": "numberOfRepeatsAllowed",
                            "valueInteger": 5
                        }
                    ]
                }
            ],
            "identifier": {
                "system": "https://provider.nhs.uk/data-identifier",
                "value": "53426283749629"
            }
        }
    ]

````
