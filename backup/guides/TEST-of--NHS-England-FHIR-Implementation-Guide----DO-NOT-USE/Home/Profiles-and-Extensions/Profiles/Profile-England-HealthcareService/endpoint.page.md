## `endpoint`

<b>Definition:</b>

Technical endpoints providing access to services operated for the specific healthcare services defined at this resource.

Endpoint identfiers to be used with the HealthcareService. Endpoints can be resolved using the SDS API

```json
"endpoint": [
        {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/nhsSpineASID", // or https://fhir.nhs.uk/Id/nhsMhsPartyKey
                "value": "999900000041"
            }
        }
    ]
```

---

