## `location`

<b>Definition:</b>

The contact address for the practitioner for the service they are providing in this role. This will often be the surgery address, clinic or service address. &#xD;&#xA;&#xD;&#xA;If using ODS Codes, the address on ODS must be checked to ensure it is correct. If the address is not correct, then *Resource reference* **MUST** be supplied.

```json
"location":  [
         {
            "identifier": {
              "system": "https://fhir.nhs.uk/Id/ods-organization-code",
              "value": "RCB55"
            }
            "display": "YORK HOSPITAL"
          }
  ]
```

For EPS, currently a *Resource reference* is required.

```json
"location":  [
         {
            "reference": "urn:uuid:ecc2db8e-3757-4758-a4f1-7f4c7e06662f",
            "display": "YORK HOSPITAL"
          }
  ]
```

---

