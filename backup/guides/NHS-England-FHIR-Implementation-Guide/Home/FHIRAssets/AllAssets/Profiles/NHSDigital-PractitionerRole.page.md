## NHSDigital-PractitionerRole


| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole) | {{pagelink:Administration}} | normative | 

<br>

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation"  class="active">
            <a href="#Combined" role="tab" data-toggle="tab">Combined</a>
        </li>
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab">Differential</a>
        </li>
          <li role="presentation">
            <a href="#Constraints" role="tab" data-toggle="tab">Constraints</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
       
        <div id="Combined" role="tabpanel" class="tab-pane active">
            <br>
 {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
     from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole}} <br> 
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole, diff}}
        </div>
           <div id="Constraints"  class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples"  class="tab-pane">

<br />

- {{pagelink:PractitionerRole---SDS---NHS-1}}
- {{pagelink:PractitionerRole---SDS---NHS-2}}
- {{pagelink:PractitionerRole---SDS-Only-Variant}}

<br />

</div>
</div>

### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
```


<br/>

<br/>

 #### Definition

 A specific set of Roles/Locations/specialties/services that a practitioner may perform at an organization for a period of time.

 #### Constraints 

- **role-spurious** (*WARNING*) Spurious Code format must be G6NNNNNN or G7NNNNNN
- **role-sds-role-profile** (*ERROR*) SDS Role Profile Id must be 12 digits


- <a href="#extension:costCentre">extension:costCentre</a>
- <a href="#identifier">identifier</a>
- <a href="#identifier:sdsRoleProfileID">identifier:sdsRoleProfileID</a>
- <a href="#identifier:sdsRoleProfileID.system">identifier:sdsRoleProfileID.system</a>
- <a href="#identifier:nhsbsaSpuriousCode">identifier:nhsbsaSpuriousCode</a>
- <a href="#identifier:nhsbsaSpuriousCode.system">identifier:nhsbsaSpuriousCode.system</a>
- <a href="#practitioner">practitioner</a>
- <a href="#organization">organization</a>
- <a href="#code">code</a>
- <a href="#code.coding:sdsJobRoleCode">code.coding:sdsJobRoleCode</a>
- <a href="#code.coding:sdsJobRoleCode.system">code.coding:sdsJobRoleCode.system</a>
- <a href="#specialty">specialty</a>
- <a href="#specialty.coding:NHSDataDictionarySpecialty">specialty.coding:NHSDataDictionarySpecialty</a>
- <a href="#specialty.coding:NHSDataDictionarySpecialty.system">specialty.coding:NHSDataDictionarySpecialty.system</a>
- <a href="#specialty.coding:SNOMEDSpecialty">specialty.coding:SNOMEDSpecialty</a>
- <a href="#specialty.coding:SNOMEDSpecialty.system">specialty.coding:SNOMEDSpecialty.system</a>
- <a href="#location">location</a>
- <a href="#healthcareService">healthcareService</a>
- <a href="#telecom">telecom</a>

<a name="extension:costCentre"></a>
 ## extension:costCentre

| | |
|----|----|
|Element Id|PractitionerRole.extension:costCentre|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|costCentre|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionNHSDigitalAccountCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-NHSDigital-Account-code))|

<br/>

 #### Definition

 Optional Extension Element - found in all resources.

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|PractitionerRole.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 | FHIR identifier | OID/HL7v3 | HL7v2 ITK | Format | Description | Professional Code  | Prescribing Code | 
|--|--|--|--|--|--|--|
| https://fhir.hl7.org.uk/Id/nhsbsa-spurious-code |  |  | G[67]NNNNNN | NHS BSA Spurious Code [GENERAL MEDICAL PRACTITIONER PPD CODE](https://datadictionary.nhs.uk/attributes/general_medical_practitioner_ppd_code.html) | No | Yes |
| https://fhir.nhs.uk/Id/sds-role-profile-id | 1.2.826.0.1285.0.2.0.67 | | 12 digits | SDS Role Profile Code | No | No | 

The *SDS Role Profile Code* should be sourced from NHS Identity (SmartCard), this is also held within the Spine Directory Service LDAP database.

Holds *NHS BSA spurious codes* which are role specific *Doctor Index Number (DIN)*) codes. *NHS BSA spurious codes* are issued when a doctor issues medication outside of their normal role, normally at another organisation. In the example below, the doctor is working in a secondary role (with SDS Role Id of 100102238986), as this a has a spurious code of 2345213. If the doctor was prescribing in their primary role this *spurious code* would be absent.

```json
{
  "resourceType": "PractitionerRole",
  ...
  "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/sds-role-profile-id",
            "value": "100102238986"
          },
          {
            "system": "https://fhir.hl7.org.uk/Id/nhsbsa-spurious-code",
            "value": "2345213"
          }
        ],
  ...
}
```

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:sdsRoleProfileID"></a>
 ## identifier:sdsRoleProfileID

| | |
|----|----|
|Element Id|PractitionerRole.identifier:sdsRoleProfileID|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|sdsRoleProfileID|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier that applies to this person in this role.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:sdsRoleProfileID.system"></a>
 ## identifier:sdsRoleProfileID.system

| | |
|----|----|
|Element Id|PractitionerRole.identifier:sdsRoleProfileID.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/sds-role-profile-id|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:nhsbsaSpuriousCode"></a>
 ## identifier:nhsbsaSpuriousCode

| | |
|----|----|
|Element Id|PractitionerRole.identifier:nhsbsaSpuriousCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|nhsbsaSpuriousCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier that applies to this person in this role.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:nhsbsaSpuriousCode.system"></a>
 ## identifier:nhsbsaSpuriousCode.system

| | |
|----|----|
|Element Id|PractitionerRole.identifier:nhsbsaSpuriousCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/nhsbsa-spurious-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="practitioner"></a>
 ## practitioner

| | |
|----|----|
|Element Id|PractitionerRole.practitioner|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner))|

<br/>

 #### Definition

 This **MUST** either be a reference to a Practitioner resource or an identifier reference plus a display. In both cases the referenced resource or identifier reference should contain a professional code. 

It is recommended an *identifier reference* and *display* (practitioner full name) is included. This identifier should be the Practitioner's primary professional code (see `NHSDigital-Practitioner` for details on professional codes). 

```json
"practitioner": {
        "display": "Dr Smith",
        "identifier": {
            "system": "https://fhir.hl7.org.uk/Id/gmc-number",
            "value": "C9876543"
          }
    },
```

For EPS, currently a *Resource reference* is required.

```json
"practitioner": {
        "reference": "urn:uuid:1557E58E-3B1E-41DD-B3B5-D4D393DC5A3D",
        "display": "Dr Smith"
    },
```

 #### Constraints 

- **nhsd-2** (*WARNING*) An identifier reference or resource reference must be provided
- **role-nmc** (*WARNING*) NMC must be of the format NNANNNNA
- **role-gmp** (*ERROR*) GMP must be of the format GNNNNNNN and not be a spurious code (starts with G6 or G7)
- **role-gmc** (*ERROR*) GMC must be of the format CNNNNNNN
- **role-gphc** (*WARNING*) GPHC must be of the format NNNNNNN
- **role-hcpc** (*WARNING*) HCPC must be of the format AANNNNNN
- **role-din** (*WARNING*) DIN format must be NNNNNN
- **role-sds-user-numeric** (*ERROR*) sds-user-id must be numeric
- **role-gmcreferencenumber** (*ERROR*) GMC Reference Number must be of the format NNNNNNN
- **nacs-code-retired** (*WARNING*) NACS (/ODS) Practitioner Identifier is retired in NHS FHIR and should not be used. Please use the actual naming system instead (e,g, https://fhir.hl7.org.uk/Id/gmc-number, https://fhir.hl7.org.uk/Id/gmp-number, etc).

<a name="organization"></a>
 ## organization

| | |
|----|----|
|Element Id|PractitionerRole.organization|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization))|

<br/>

 #### Definition

 This **MUST** either be a reference to a Organization resource or an identifier reference. In both cases the reference must contain an ANANA/ODS organisation code. 


#### organisation resource references

It is recommended an *identifier reference* is included. 

```json
"organization": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RBA"
          },
        "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
    }
```

Optionally *Resource reference* can be provided. This is required in the current version of EPS but this will be changed to supporting the *identifier reference* only.

```json
"organization": {
        "reference": "urn:uuid:17c4270d-6966-4788-8cbc-1d1d63536b25",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RBA"
          },
        "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
    }
```

 #### Constraints 

- **nhsd-1** (*WARNING*) PractitionerRole.organization - An identifier reference or resource reference should be provided

<a name="code"></a>
 ## code

| | |
|----|----|
|Element Id|PractitionerRole.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDigitalPractitionerRoleCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-PractitionerRoleCode) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Only supply if this is known from SmartCard/CIS2 data.

```json
"code":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/NHSDigital-SDS-JobRoleCode",
                    "code": "S0030:G0100:R0620"
                  }
            ]
        }
    ],
```

The previous system for this entry was `https://fhir.hl7org.uk/CodeSystem/UKCore-SDSJobRoleName`, this has been retired and `https://fhir.nhs.uk/CodeSystem/NHSDigital-SDS-JobRoleCode` should be used instead.

 #### Requirements

 Need to know what authority the practitioner has - what can they do?

 #### Comment

 A person may have more than one role.

<a name="code.coding:sdsJobRoleCode"></a>
 ## code.coding:sdsJobRoleCode

| | |
|----|----|
|Element Id|PractitionerRole.code.coding:sdsJobRoleCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|sdsJobRoleCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 This value should be sourced from either APIM OAuth2 userinfo endpoint, SDS LDAP or CIS2/SmartCard details. 

The CodeSystem is variable and is not present in this Implementation Guide.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="code.coding:sdsJobRoleCode.system"></a>
 ## code.coding:sdsJobRoleCode.system

| | |
|----|----|
|Element Id|PractitionerRole.code.coding:sdsJobRoleCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/NHSDigital-SDS-JobRoleCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="specialty"></a>
 ## specialty

| | |
|----|----|
|Element Id|PractitionerRole.specialty|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[PracticeSettingCodeValueSet](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/c80-practice-codes) (Preferred) <br/>Specific specialty associated with the agency. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 This is should be the specialty linked to the role and is not necessarily the practitioners main specialty. 

This can be supplemented by SNOMED CT codes from {{link:http://hl7.org/fhir/ValueSet/c80-practice-codes}}, no ConceptMap currently exists for mapping between the two.

```json
 "specialty": [
        {
            "coding": [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/NHSDataModelAndDictionary-clinical-specialty",
                    "code": "100",
                    "display": "GENERAL SURGERY"
                }
            ]
        }
    ],
```

<a name="specialty.coding:NHSDataDictionarySpecialty"></a>
 ## specialty.coding:NHSDataDictionarySpecialty

| | |
|----|----|
|Element Id|PractitionerRole.specialty.coding:NHSDataDictionarySpecialty|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDataDictionaryMainClinicalSpecialty](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDataModelAndDictionary-clinical-specialty) (Required) <br/>NHS Data Dictionary Specialty |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|NHSDataDictionarySpecialty|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="specialty.coding:NHSDataDictionarySpecialty.system"></a>
 ## specialty.coding:NHSDataDictionarySpecialty.system

| | |
|----|----|
|Element Id|PractitionerRole.specialty.coding:NHSDataDictionarySpecialty.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/NHSDataModelAndDictionary-clinical-specialty|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="specialty.coding:SNOMEDSpecialty"></a>
 ## specialty.coding:SNOMEDSpecialty

| | |
|----|----|
|Element Id|PractitionerRole.specialty.coding:SNOMEDSpecialty|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[PracticeSettingCodeValueSet](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/c80-practice-codes) (Preferred) <br/>Specific specialty associated with the agency. |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|SNOMEDSpecialty|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="specialty.coding:SNOMEDSpecialty.system"></a>
 ## specialty.coding:SNOMEDSpecialty.system

| | |
|----|----|
|Element Id|PractitionerRole.specialty.coding:SNOMEDSpecialty.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|http://snomed.info/sct|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="location"></a>
 ## location

| | |
|----|----|
|Element Id|PractitionerRole.location|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalLocation](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Location))|

<br/>

 #### Definition

 The contact address for the practitioner for the service they are providing in this role. This will often be the surgery address, clinic or service address. 

If using ODS Codes, the address on ODS must be checked to ensure it is correct. If the address is not correct, then *Resource reference* **MUST** be supplied.

```json
"location":  [
         {
            "identifier": {
              "system": "https://fhir.nhs.uk/Id/ods-organization-code",
              "value": "RCB55"
            }
            "display": "YORK HOSPITAL"
          }
  ]
```

For EPS, currently a *Resource reference* is required.

```json
"location":  [
         {
            "reference": "urn:uuid:ecc2db8e-3757-4758-a4f1-7f4c7e06662f",
            "display": "YORK HOSPITAL"
          }
  ]
```

 #### Constraints 

- **nhsd-3** (*ERROR*) PractitionerRole.location - An identifier or resource reference must be provided

<a name="healthcareService"></a>
 ## healthcareService

| | |
|----|----|
|Element Id|PractitionerRole.healthcareService|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalHealthcareService](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService))|

<br/>

 #### Definition

 **SHOULD** be provided for a practitioner in secondary care and will be a reference to clinic or service. This referenced resource or the identifier reference **SHOULD** contain a ODS/ANANA identifier. In secondary care Electronic Prescription Service (EPS) this will also be called **prescribing cost centre**. This is used for reimbursements from NHS BSA. In secondary care the healthcare/service cost centre may also be the ODS code for the clinic.


#### healthcareService Resource reference

An *identifier reference* **MUST** be included. For secondary care organisations this will be the ODS/ANANA Cost Centre code given to a clinic. 

```json
"healthcareService":  
    [
         {
            "identifier": {
              "system": "https://fhir.nhs.uk/Id/ods-organization-code",
              "value": "A99968"
            }
            "display": "SOMERSET BOWEL CANCER SCREENING CENTRE"
          }
    ]
```

Optionally *Resource reference* can be provided. This is required in the current version of EPS but this will be changed to supporting the *identifier reference* only.

```json
"healthcareService":  
    [
         {
            "reference": "urn:uuid:54b0506d-49af-4245-9d40-d7d64902055e",
            "identifier": {
              "system": "https://fhir.nhs.uk/Id/ods-organization-code",
              "value": "A99968"
            }
            "display": "SOMERSET BOWEL CANCER SCREENING CENTRE"
          }
    ]
```

 #### Constraints 

- **nhsd-4** (*ERROR*) PractitionerRole.healthcareService - An identifier reference or resource reference must be provided

<a name="telecom"></a>
 ## telecom

| | |
|----|----|
|Element Id|PractitionerRole.telecom|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[ContactPoint](https://www.hl7.org/fhir/datatypes.html#ContactPoint)|

<br/>

 #### Definition

 At least one **telecom** number **MUST** be provided. 
Contact details that are specific to the role/location/service. Often practitioners have a dedicated line for each location (or service) that they work at and need to be able to define separate contact details for each of these. 

This is not the personnel contact number of the Practitioner, it the contact number for the practitioner in this role and may be the phone number of the clinic, main or branch surgery. 

```json
"telecom": [
          {
            "system": "phone",
            "value": "01234567890",
            "use": "work"
          }
        ]
```

 #### Requirements

 Often practitioners have a dedicated line for each location (or service) that they work at, and need to be able to define separate contact details for each of these.