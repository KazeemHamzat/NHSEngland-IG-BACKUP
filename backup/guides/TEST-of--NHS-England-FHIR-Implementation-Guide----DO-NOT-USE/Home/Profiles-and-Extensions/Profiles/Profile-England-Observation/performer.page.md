## `effective[x]`

<b>Definition:</b><br>

Who was responsible for asserting the observed value as "true".

```json
"performer": [
  {
    "type": "Organization",
    "identifier": {
      "type": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/CodeSystem/England-OrganisationRole",
            "code": "173",
            "display": "PATHOLOGY LAB"
          }
        ]
      },
      "value": "LFD004"
    }
  },
  {
    "type": "Organization",
    "identifier": {
      "type": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/Id/OrgType",
            "code": "TestCentreId",
            "display": "Testing Centre"
          }
        ]
      },
      "value": "WKE03"
    }
  }
]
```

---