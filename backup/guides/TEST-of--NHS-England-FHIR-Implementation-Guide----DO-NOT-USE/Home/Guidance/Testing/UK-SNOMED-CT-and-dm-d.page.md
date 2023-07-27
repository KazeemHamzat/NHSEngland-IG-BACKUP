## {{page-title}}

It is not currently possible to validate UK terminology using HL7 Validation. The HL7 Validator will by default validate against international SNOMED CT. This validation can be disabled by via the `-tx n/a` parameter. 

It is recommended to directly use the [NHS Digital Terminology Server](https://digital.nhs.uk/services/terminology-servers) to validate UK SNOMED and dm+d coding. 
This is FHIR R4 terminology server which contains UK SNOMED and dm+d CodeSystem. It supports terminology operations such as `$validate-code` which allows a SNOMED CT code to be checked against a `FHIR (SNOMED) ValueSet. 

<br/>