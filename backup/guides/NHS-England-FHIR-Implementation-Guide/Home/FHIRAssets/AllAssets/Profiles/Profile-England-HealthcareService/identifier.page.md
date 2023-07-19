## `identifier`

<b>Definition:</b>

**SHOULD** contain the service identifier e.g. the serviceId from <a href="https://www.directoryofservices.nhs.uk/">Directory of Service</a> or <a href="https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir">e-RS Directory Services</a>

**MAY** contain an ANANA/ODS code.

```json
"identifier": [
          {
            "use": "official",
            "system": "https://fhir.nhs.uk/Id/ers-service",
            "value": "11021"
          }
        ]
```