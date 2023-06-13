## {{page-title}}

### NHS Digital Profiles

NHS Digital profiles build on [UKCore profiles](https://simplifier.net/guide/ukcoreversionhistory/home). They extend the UK definitions by adding England and NHS Digital data models, documentation and constraints. From a FHIR perspective they will have a `baseDefinition` which will be a UK Core profile.

Diagram below shows the NHS Digital focused additional documentation:

<img src="https://raw.githubusercontent.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/master/Diagams/constraint-nhsdigital.png" width="100%"/>

The scope of these profiles is NHS Digital API's and they will have a definition of 

`https://fhir.nhs.uk/StructureDefinition/NHSDigital-{resourceName}`

e.g.

[https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole) 

#### profile constraints

NHS Digital profiles make use of [FHIRPath](https://hl7.org/fhirpath/) based constraints. 

The diagram below shows expressions on NHSDigital-PractitionerRole.practitioner which enforce/test consistency with the [NHS Data Dictionary](https://www.datadictionary.nhs.uk/) 

<img src="https://raw.githubusercontent.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/master/Diagams/constraint-fhirpath.png" width="60%"/>

<br/>

Note: a more human readable version of these practitioner constraints is available in [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner) in the identifier section.

<br/>

### NHS Digital Constraint Profiles

In addition we have `constraint` profiles which will add API specific constraints to NHS Digital (or UKCore) profiles. They will be of the format:


`https://fhir.nhs.uk/StructureDefinition/NHSDigital-{resourceName}-{constraintName}`

e.g. 

[https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-Minimal](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-Minimal) 

This profile has a baseDefinition of [https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole) and adds in mandatory constraints to `practitioner` plus `organization`.


<br/>

<img src="https://raw.githubusercontent.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/master/Diagams/constraint-profile.png" width="50%"/>

<br/>




