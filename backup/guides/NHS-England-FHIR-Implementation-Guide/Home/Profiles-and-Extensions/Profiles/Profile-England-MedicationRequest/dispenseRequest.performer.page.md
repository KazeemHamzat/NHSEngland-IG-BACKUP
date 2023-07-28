## `dispenseRequest.performer`

<b>Definition</b><br>

For non token based prescriptions the destination pharmacy **MUST** be recorded in the *dispenseRequest.performer.identifier* and a identifier reference (not a resource reference) with an ANANA/ODS Code **MUST** used. 

The extension 
https://fhir.nhs.uk/StructureDefinition/Extension-England-DMPerformerSiteType         **MUST** be present.

Patients pharmacy preferences may be sourced from PDS.

Patients pharmacy preferences may be overriden by an 'one-off pharmacy nomination' by populating the *dispenseRequest.performer.identifier* with the ODS/ANANA code of the destination pharmacy.

<br>

```json
"dispenseRequest": {
        "extension":  [
            {
                "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PerformerSiteType",
                "valueCoding": {
                    "system": "https://fhir.nhs.uk/CodeSystem/dispensing-site-preference",
                    "code": "0004"
                }
            },
        ],
        "performer": {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "FX748"
            }
        },
```

---