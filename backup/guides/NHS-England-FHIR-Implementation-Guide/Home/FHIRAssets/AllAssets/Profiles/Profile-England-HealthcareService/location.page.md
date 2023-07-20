## `location`

<b>Definition:</b>

Reference to a location. ODS codes may be used, however this may differ from Directory of Services and so DoS addresses are preferred.

```json
 "location":  [
        {
            "reference": "urn:uuid:8a5d7d67-64fb-44ec-9802-2dc214bb3dcb"
        }
    ],
```

or

```json
"location": [
        {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-site-code",
                "value": "R6901"
            }
        }
    ],
```

---

