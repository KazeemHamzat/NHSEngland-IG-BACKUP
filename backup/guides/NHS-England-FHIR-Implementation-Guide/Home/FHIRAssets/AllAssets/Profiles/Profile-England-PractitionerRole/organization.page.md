## `organization`

<b>Definition:</b>

This **MUST** either be a reference to a Organization resource or an identifier reference. In both cases the reference must contain an ANANA/ODS organisation code.

#### organisation resource references

It is recommended an *identifier reference* is included.

```json
"organization": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RBA"
          },
        "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
    }
```

Optionally *Resource reference* can be provided. This is required in the current version of EPS but this will be changed to supporting the *identifier reference* only.

```json
"organization": {
        "reference": "urn:uuid:17c4270d-6966-4788-8cbc-1d1d63536b25",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RBA"
          },
        "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
    }
```

---

