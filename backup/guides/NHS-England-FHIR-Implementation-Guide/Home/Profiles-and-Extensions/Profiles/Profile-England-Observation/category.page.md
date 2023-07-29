## `category`

<b>Definition:</b><br>

This is an optional element. If used the category will always be <code>laboratory</code>.

```json
 "category":  [
        {
            "coding":  [
                {
                    "system": "http://terminology.hl7.org/CodeSystem/observation-category",
                    "code": "laboratory",
                    "display": "Laboratory"
                }
            ],
            "text": "Laboratory"
        }
    ],
```

For COVID-19 Tests, the ValueSet SHOULD be used to indicate which test pillar the observation originated.

```json
 "category": [
        {
            "coding": [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/England-CovidTestPillar",
                    "code": "pillar-1",
                    "display": "pillar 1"
                }
            ]
        }
    ],
```

---