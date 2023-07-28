### {{page-title}}

 <div markdown="span" class="alert alert-warning" role="alert">
 <i class="fas fa-exclamation-circle"></i><b> Important:</b> This page is under development by NHS Digital</div>

[FHIR Validation](https://www.hl7.org/fhir/validation.html) SHOULD be used with this implementation guide. 

This IG and FHIR Validation currently tests the following:

<table class="regular assets" style="width:100%">
 <thead>
   <tr>
     <th width="20%">Aspect</th>
     <th width="5%">Verified</th>
     <th width="50%">Description</th>
     <th width="25%">Notes</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
      Structure
    </td>
     <td>
      &#x2705;
    </td>
    <td>
    Check that all the content in the resource is described by the specification, and nothing extra is present
    </td>
    <td>
    XML, JSON and RDF
    </td>
    </tr>
    <tr>
    <td>
    Cardinality
    </td>
     <td>
      &#x2705;
    </td>
    <td>
  Check that the cardinality of all properties is correct (min & max)
    </td>
    <td>
 
    </td>
    </tr>
       <tr>
    <td>
    Value Domains
    </td>
     <td>
      &#x2705;
    </td>
    <td>
  Check that the values of all properties conform to the rules for the specified types (including checking that enumerated codes are valid)
    </td>
    <td>
 
    </td>
    </tr>
         <tr>
    <td>
    Coding/CodeableConcept bindings
    </td>
     <td>
        &#x2705;
    </td>
    <td>
  Check that codes/displays provided in the Coding/CodeableConcept types are valid
    </td>
    <td>
 This requires a <a href="https://ontology.nhs.uk/" target="_blank">UK Terminology Server</a> and currently it is not possible to use this directly with FHIR Validation tools. 
 <br/>
 Is supported in <a href="https://github.com/NHSDigital/validation-service-fhir-r4/tree/main2">NHS Digital validation-service-fhir-r4</a> 
    </td>
    </tr>
         <tr>
    <td>
    Invariants
    </td>
     <td>
      &#x2705;
    </td>
    <td>
  Check that the invariants (co-occurrence rules, etc.) have been followed correctly
    </td>
    <td>
 
    </td>
    </tr>
         <tr>
    <td>
    Profiles
    </td>
     <td>
      &#x2705;
    </td>
    <td>
  Check that any rules in profiles have been followed (including those listed in the Resource.meta.profile, or in CapabilityStatement, or in an ImplementationGuide, or otherwise required by context)
    </td>
    <td>
 
    </td>
    </tr>
         <tr>
    <td>
    Questionnaires
    </td>
     <td>
      &#x2705;
    </td>
    <td>
  Check that a QuestionnaireResponse is valid against its matching Questionnaire
    </td>
    <td>
 
    </td>
    </tr>
         <tr>
    <td>
    Message Definitions
    </td>
     <td>
      &#x2705;
    </td>
    <td>
  Check that a Bundle (type=message) is valid against its matching MessageDefinition
    </td>
    <td>
 Not supported in HL7 Validation tools but is supported in 
<a href="https://github.com/NHSDigital/validation-service-fhir-r4/tree/main2">NHS Digital validation-service-fhir-r4</a> 
    </td>
    </tr>
     <tr>
    <td>
    Operation Definitions
    </td>
     <td>
      &#x2718;
    </td>
    <td>
      Support for FHIR Operations
    </td>
    <td>
  Not currently supported. 
    </td>
    </tr>
        <tr>
    <td>
   Business Rules
    </td>
     <td>
      &#x2718;
    </td>
    <td>
  Business rules are made outside the specification, such as checking for duplicates, checking that references resolve, checking that a user is authorized to do what they want to do, etc.
    </td>
    <td>
Business rules are beyond the scope of the FHIR Implementation Guide.
    </td>
    </tr>
</tbody>
</table>

#### HL7 FHIR Validator

When [using the FHIR Validator](https://www.hl7.org/fhir/validation.html#jar), the general format will be:

`java -jar validator_cli.jar [filename] -version 4.0.1 -ig [nhs-digital-ig-package] -profile [profile]`

Where 
- **filename** is the file name of the resource being validated.
- **nhs-digital-ig-package** is the url of the NHS Digital IG Package which can be found in the {{pagelink:downloads}} section
- **profile** the URI of the profile to validate against.

e.g. 

To validate a patient example against NHS Digital IG profile `NHSDigital-Patient`

`java -jar validator_cli.jar patient-ex.xml -version 4.0.1 -ig uk.nhsdigital.r4 -profile https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient`

To validate a patient example against UKCore IG profile `UKCore-Patient`

- using UKCore IG

`java -jar validator_cli.jar patient-ex.xml -version 4.0.1 -ig fhir.r4.ukcore.stu1 -profile https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient`


#### Online HL7 FHIR Validation  

[https://validator.fhir.org/](https://validator.fhir.org/) provides an online method of validating FHIR. 

Note: Validation will be performed against base FHIR and international FHIR, UK SNOMED and UK Implementation Guides are configured under `Options`. The profile is currently specified by adding a `meta.profile` to the resource. E.g.

```json
{
    "resourceType": "Task",
    "id": "dea023fc-b6ef-4419-b98f-9f209fd25ed4",
    "meta" : {
        "profile" : [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task"
        ]
    },
```

#### Asking a FHIR Server

See Operation [$validate](https://hl7.org/fhir/resource-operation-validate.html) for details.

**NHS Digital** has implemented this operation as a service and is available on GitHub [validation-service-fhir-r4](https://github.com/NHSDigital/validation-service-fhir-r4). This project has two branches:
- `main2` which is used CI/CD to validate FHIR Implementation Guides.
- `master` which is used currently by Electronic Prescription Service (EPS) to validate incoming FHIR resources.  

This is built on top of the HL7 Validator code base and extends this to cover:
- FHIR Message validation using FHIR MessageDefinition
- UK Terminology validation using OAuth2 authorisation support

<br/>