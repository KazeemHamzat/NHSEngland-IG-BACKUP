## {{page-title}}

When validating against a NHS Digital IG, the NHS Digital IG package should be used. This can be found in the {{pagelink:Downloads}} section. This package will include the corresponding UKCore package automatically.

### Profiles

The `UKCore` profiles are the default profiles for UK FHIR Validation. 
For {{pagelink:Administration}} resources such as Patient, Organization, Practitioner, PractitionerRole, etc, `NHSDigital` profiles should be used instead. These profiles are derivatives of UKCore which contain additional English NHS rules and constraints.

### Example Using HL7 Validation using UKCore profile 

The local file *medicationrequest.json* is validated against *UKCore-MedicationRequest*

`java -jar validator_cli.jar medicationrequest.json -version 4.0.1 -tx n/a -ig uk.nhsdigital.r4 -profile https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest`

Note: the `uk.nhsdigital.r4` is used for validation as it contains UKCore.

### Example Using HL7 Validation using NHSDigital profile

The local file *practitioner.json* is validated against *NHSDigital-Practitioner*

`java -jar validator_cli.jar practitioner.json -version 4.0.1 -tx n/a -ig uk.nhsdigital.r4 -profile https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner`

To validate against `UKCore-Practitioner` this becomes: 

`java -jar validator_cli.jar practitioner.json -version 4.0.1 -tx n/a -ig uk.nhsdigital.r4 -profile https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner`


<br/>




