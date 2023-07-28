## `basedOn.extension:repeatInformation`

<b>Definition</b><br>

The extension `numberOfRepeatsIssued` should not be populated.The meaning of `numberOfRepeatsAllowed` is the same as the dispensingRequest.numberOfRepeatsAllowed. 

An integer indicating the number of times, in addition to the original dispense (refills or repeats) that the patient can receive the prescribed medication. 

- Usage Notes: This integer does not include the original order dispense. This means that if an order indicates dispense 30 tablets plus 3 repeats then the order can be dispensed a total of 4 times and the patient can receive a total of 120 tablets. A prescriber may explicitly say that zero refills are permitted after the initial dispense.

<br>

```json 
"extension": [
                {
                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation",
                    "extension": [
                        {
                            "url": "numberOfRepeatsAllowed",
                            "valueInteger": 2
                        }
                    ]
                }
            ]
```

---


    