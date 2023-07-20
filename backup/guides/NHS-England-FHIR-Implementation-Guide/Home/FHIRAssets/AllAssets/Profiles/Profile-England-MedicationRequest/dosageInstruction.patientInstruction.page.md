## `dosageInstruction.patientInstruction`

<b>Definition</b><br>

These sections **MUST** be used only be used to pass notes regarding the prescription to the pharmacist or patient. Lists of repeat medications and general practice notifications to the patient **SHOULD** be recorded in [NHSDigital-CommunicationRequest](https://simplifier.net/guide/nhsdigital/NHSDigital-CommunicationRequest).

Patient instructions for taking the drug are contained with in the `patientInstruction` and `additionalInstruction` as per the guidance in [Dosage Structure Overview](https://developer.nhs.uk/apis/dose-syntax-implementation/dosage-overview.html).

<br>

```json

"dosageInstruction": [
    {
        "text": "10 milligram, Inject, Subcutaneous route, once weekly",
        "additionalInstruction": [
            "coding": [
                {
                    "system": "http://snomed.info/sct",
                    "code": "421769005",
                    "display": "Follow directions"
                }
            ],
        ],
        "patientInstruction": "As directed"
    }
]

```
 