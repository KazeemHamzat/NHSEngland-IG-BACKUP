## `extension:repeatInformation`

<b>Definition:</b><br>

The extension is mandatory for continuous and continuous-repeat-dispensing. The following elements MUST be populated.

- numberofRepeatsAllowed
- numberOfRepeatsIssued

```json
"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-EPSRepeatInformation",
        "extension": [
            {
                "url" : "numberOfRepeatsAllowed",
                "valueInteger" : 6
            },
            {
                "url" : "numberOfRepeatsIssued",
                "valueInteger" : 2
            }
        ]
    }
]
```

---