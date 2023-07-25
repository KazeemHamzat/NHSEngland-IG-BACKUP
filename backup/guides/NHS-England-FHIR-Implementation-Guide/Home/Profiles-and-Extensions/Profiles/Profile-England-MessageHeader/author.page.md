## `author`

<b>Definition</b><br>

If present, this **SHOULD** be an identifier reference to a `Practitioner` or `PractitionerRole`. Internal references to resources should **NOT** be used.
<br>
```json
"author": {
    "type": "PractitionerRole",
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/sds-role-profile-id",
        "value": "100102238986"
    },
    "display": "DR ALI"
},
```

---