## `generalPractitioner`

<b>Definition:</b>

GP Surgery **SHOULD** be provided. It is recommended the patients GP Surgery is the first item in the array and branch surgery is second. It is also suggested type and display (name of practice) is also included.

```json
"generalPractitioner":  [
{
  "type": "Organization"
  "identifier": {
    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
    "value": "Y12345"
  },
  "display": "Kirkgate Practice"
}
]
```

---