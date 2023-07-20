## `focus`

<b>Definition</b><br>

The focus element of the MessageHeader specifies the content of the message. The MessageHeader is followed by other resources depending on the type of request. For example, a request to book an appointment may contain the Patient to book the appointment for, the Practitioner to book the appointment with and the actual Appointment that is requested.


The focus section SHOULD match the focus section of the corresponding MessageDefinition

MessageDefinition.focus extract

```json
"focus":  [
        {
            "code": "MedicationRequest",
            "profile": "https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest",
            "min": 1,
            "max": "4"
        },
        {
            "code": "Patient",
            "profile": "https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient",
            "min": 1,
            "max": "1"
        },
        {
            "code": "CommunicationRequest",
            "profile": "https://fhir.nhs.uk/StructureDefinition/DM-CommunicationRequest",
            "min": 0,
            "max": "*"
        }
    ],
```
### Corresponding MessageHeader.focus (Note: type is not required and is included for illustration purposes)

```json
"focus": [
    {
        "type": "Patient",
        "reference": "urn:uuid:78d3c2eb-009e-4ec8-a358-b042954aa9b2"
    },
    {
        "type": "MedicationRequest",
        "reference": "urn:uuid:a54219b8-f741-4c47-b662-e4f8dfa49ab6"
    },
    {
        "type": "CommunicationRequest",
        "reference": "urn:uuid:28828C55-8FA7-42D7-916F-FCF076E0C10E"
    }
],
```

---