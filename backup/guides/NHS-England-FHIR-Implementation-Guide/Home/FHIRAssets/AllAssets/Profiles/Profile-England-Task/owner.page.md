## `owner`

<b>Definition</b><br>

**EPS**

Who is responsible for actioning the request Task (e.g. for a prescription-order this will be the pharmacy). 

```json
"owner": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "FB444"
        },
        "display": "Freds Pharmacy"
    },
```

**e-RS**

```json
"owner": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ers-service",
            "value": "12444"
        }
    },
```

---