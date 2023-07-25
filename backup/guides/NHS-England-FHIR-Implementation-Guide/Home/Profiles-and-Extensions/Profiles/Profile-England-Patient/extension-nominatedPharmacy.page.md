## `extension:nominatedPharmacy`

<b>Definition:</b>

A patient can choose up to three nominated dispensers to cover different contractor types:

- Community Pharmacy
- Appliance Contractor
- Dispensing Doctor

Each of those nominations is held in an Extension.

All require a ODS/ANANA code from [Organisation Data Services](https://digital.nhs.uk/services/organisation-data-service). This contains download CSV files for these organisations, for API access please see  [Organisation Data Service - FHIR API](https://digital.nhs.uk/developer/api-catalogue/organisation-data-service-fhir)
<br>
#### nominatedPharmacy (extension nominatedPharmacy)

```json
"extension":  [
        {
            "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NominatedPharmacy",
            "valueReference": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "Y12345"
                }
            }
        },
```

---