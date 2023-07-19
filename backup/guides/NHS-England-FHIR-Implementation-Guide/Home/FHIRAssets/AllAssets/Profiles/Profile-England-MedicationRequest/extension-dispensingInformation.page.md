## `extension:dispensingInformation`

<b>Definition:</b><br>

This extension is used in `continuous-repeat-dispensing` prescriptions sent by EPS to dispensing systems to convey information on prior dispensed medications.

```json
  
https: //fhir.nhs.uk/StructureDefinition/Extension-EPS-DispensingInformation;
;
extension;
: [{ ;
        url;
        dispenseStatus; ;
        valueCoding;
        : { ;
            system;
            https: //fhir.nhs.uk/CodeSystem/medicationdispense-type;
        ;
            code;
            0001; ;
            display;
            Item fully dispensed;
        }
    }, { ;
        url;
        dateLastDispensed; ;
        valueDateTime;
        2018 - 04 - 22T09: 57: 03 + 00: 00;
    }
]