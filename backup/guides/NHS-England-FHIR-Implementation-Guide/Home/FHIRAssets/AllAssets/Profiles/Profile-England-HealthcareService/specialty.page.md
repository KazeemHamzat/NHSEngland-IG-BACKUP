## `specialty`

<b>Definition:</b>

Specialty **SHOULD** be from the {{link:http://hl7.org/fhir/ValueSet/c80-practice-codes}} and is the SNOMED equivalent of the [NHS Data Dictionary - Main Specialty and Treament Function Codes](https://datadictionary.nhs.uk/supporting_information/main_specialty_and_treatment_function_codes_table.html) and FHIR {{pagelink: NHSDataDictionaryClinicalSpecialty.md}}

```json
"specialty":  [
        {
            "coding":  [
                {
                    "system": "http://snomed.info/sct",
                    "code": "394579002",
                    "display": "Cardiology"
                }
            ]
        }
    ],
```

or using NHS Data Dictionary codes.

```json
"specialty":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/NHSDataModelAndDictionary-clinical-specialty",
                    "code": "320",
                    "display": "Cardiology"
                }
            ]
        }
    ],
```

or for e-RS Patient Care

```json
 "specialty": [
        {
            "coding": [
                {
                    "display": "Dermatology"
                }
            ]
        }
    ],
```

---
