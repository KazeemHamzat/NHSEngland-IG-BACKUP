## `extension:NHSBSAprescriptionType`

<b>Definition:</b><br>

The vocabulary for the ‘PrescriptionType’ vocabulary is defined within the NHSBSA Overprint Specification. 
The System must populate the ‘PrescriptionType’ attribute for the appropriate combination of prescriber and care setting. Retired codes within this vocabulary must not be used.

<br>

```json

"extension": [
    " url ": " https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionType",
    "valueCoding": {
        "system": "https://fhir.nhs.uk/CodeSystem/prescription-type",
        "code": "1201",
        "display": "Outpatient Homecare Prescriber - Medical Prescriber"
    }
]
            
````


