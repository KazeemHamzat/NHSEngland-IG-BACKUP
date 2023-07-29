## `type`

<b>Definition:</b>

Type **SHOULD** be populated.

```json
"type":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/DoS-ClinicType",
                    "code": "PHARMACY",
                    "display": "Pharmacy"
                }
            ]
        }
    ],

```

or 

```json
"type": [
        {
            "coding": [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/eRS-AppointmentType",
                    "code": "DAY_CASE",
                }
            ]
        }
    ],
```

### `type.coding:eRSAppointmentType`

Appointment type e.g. telephone/video (only applicable and mandatory if Service Type is Appointment Request, not applicable to Service Type of Triage Request)

---

