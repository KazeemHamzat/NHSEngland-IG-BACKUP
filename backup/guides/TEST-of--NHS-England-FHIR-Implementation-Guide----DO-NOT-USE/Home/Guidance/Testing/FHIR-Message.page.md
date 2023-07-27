## {{page-title}}

FHIR Messaging is a defined collection of resources in a FHIR Bundle. The definition of the message is contained within a FHIR MessageDefinition, E.g. {{pagelink:prescription-order}}. 

It is not currently possible to validate against a MessageDefinition in the HL7 Validator. 

The recommended approach with the HL7 Validator is to validate the bundle using the `-bundle` parameter with the profile specified in the MessageDefintion.focus). 

### Example EPS 

The {{pagelink:prescription-order}} MessageDefinition, specifies MedicationRequest should conform to  `https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Message`. 

{{render:Screenshot-2022-08-01-at-06.17.01}}

A prescription-order can be tested with the following command:


`java -jar validator_cli.jar prescription.json -version 4.0.1 -tx n/a -ig uk.nhsdigital.r4 -bundle MedicationRequest:0 https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Message`

The `-bundle` parameter says, test the first occurence of MedicatioRequest against the specified profile.


### Example BARS

The `bars-message-servicerequest-request-referral` main focus resource is ServiceRequest with a profile of `https://fhir.nhs.uk/StructureDefinition/BARSServiceRequest-request-referral`

An example validation command is: 

`java -jar validator_cli.jar message.json -version 4.0.1 -tx n/a -ig https://packages.simplifier.net/uk.nhsdigital.r4.test/-/uk.nhsdigital.r4.test-2.6.32-prerelease.tgz -bundle ServiceRequest:0 https://fhir.nhs.uk/StructureDefinition/BARSServiceRequest-request-referral`

The ig used is the NHSDigital development version and so the download url is specified, once this version is released this can be replaced with the normal 'uk.nhsdigital.r4' ig. 

The `-bundle` parameter says, test the first occurrence of ServiceRequest against the BARS referral profile.

### Message Conformance Profiles

EPS uses message specific profiles, i.e., it uses `NHSDigital-MedicationRequest-Message` which has additional rules to the normal `NHSDigital-MedicationRequest` (and also `UKCore-MedicationRequest`).

{{render:Screenshot-2022-08-01-at-06.25.39}}

These rules will automatically be applied by the FHIR Validator. So, although no Patient profiles were specified in the FHIR MessageDefinition, the Patient resource in the FHIR Bundle MUST contain a `nhs-number` as required by the `NHSDigital-Patient-PDS` profile.

<br/>
