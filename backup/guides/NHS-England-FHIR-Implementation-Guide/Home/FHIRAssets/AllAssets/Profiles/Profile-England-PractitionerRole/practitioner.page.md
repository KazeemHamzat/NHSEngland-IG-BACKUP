## `practitioner`

<b>Definition:</b>

This **MUST** either be a reference to a Practitioner resource or an identifier reference plus a display. In both cases the referenced resource or identfier reference should contain a professional code.

It is recommended an *identifier reference* and *display* (practioner full name) is included. This identifier should be the Practitioner's primary professional code (see `England-Practitioner` for details on professional codes).

```json
"practitioner": {
        "display": "Dr Smith",
        "identifier": {
            "system": "https://fhir.hl7.org.uk/Id/gmc-number",
            "value": "C9876543"
          }
    },
```

For EPS, currently a *Resource reference* is required.

```json
"practitioner": {
        "reference": "urn:uuid:1557E58E-3B1E-41DD-B3B5-D4D393DC5A3D",
        "display": "Dr Smith"
    },
```

---

