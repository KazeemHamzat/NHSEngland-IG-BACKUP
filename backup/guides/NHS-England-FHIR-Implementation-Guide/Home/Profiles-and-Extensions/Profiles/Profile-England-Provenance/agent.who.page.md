## `agent.who`

<b>Definition</b><br>
Actors who have responsibility for the target resource.

It is recommended practitioner professional (e.g. GMC, GMP, etc) and/or organisation ODS codes are used. However SDS id's are permitted.

This **SHOULD** use identifier references. 

```json
"agent": [
        {
            "who": {
                "identifier": {
                    "system": "https://fhir.hl7.org.uk/Id/gmc-number",
                    "value": "C9876543"
                }
            }
        }
    ],
```

---