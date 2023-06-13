## NHSDigital-HealthcareService

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService) | {{pagelink:Administration}} | trial-use |

The HealthcareService resource is used to describe a single healthcare service or category of services that are provided by an organization at a location.
The location of the services could be virtual, as with telemedicine services.


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
     {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
    {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService, diff}}
        </div>
        <div id="Constraints"  class="tab-pane">
<br/>
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples"  class="tab-pane">
<br/>

  - {{pagelink:HealthcareService}}
  - {{pagelink:HealthcareService-detailed}}
  
</div>
</div>

### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
```


---

<br/>

 #### Definition

 The details of a healthcare service available at a location.


- <a href="#identifier">identifier</a>
- <a href="#identifier:ersServiceId">identifier:ersServiceId</a>
- <a href="#identifier:ersServiceId.system">identifier:ersServiceId.system</a>
- <a href="#identifier:dosServiceId">identifier:dosServiceId</a>
- <a href="#identifier:dosServiceId.system">identifier:dosServiceId.system</a>
- <a href="#providedBy">providedBy</a>
- <a href="#providedBy.identifier.system">providedBy.identifier.system</a>
- <a href="#type">type</a>
- <a href="#type.coding:UKCoreCareSettingType">type.coding:UKCoreCareSettingType</a>
- <a href="#type.coding:UKCoreCareSettingType.system">type.coding:UKCoreCareSettingType.system</a>
- <a href="#type.coding:eRSAppointmentType">type.coding:eRSAppointmentType</a>
- <a href="#type.coding:eRSAppointmentType.system">type.coding:eRSAppointmentType.system</a>
- <a href="#specialty">specialty</a>
- <a href="#specialty.coding:NHSDataDictionarySpecialty">specialty.coding:NHSDataDictionarySpecialty</a>
- <a href="#specialty.coding:NHSDataDictionarySpecialty.system">specialty.coding:NHSDataDictionarySpecialty.system</a>
- <a href="#specialty.coding:SNOMEDPracticeCode">specialty.coding:SNOMEDPracticeCode</a>
- <a href="#specialty.coding:SNOMEDPracticeCode.system">specialty.coding:SNOMEDPracticeCode.system</a>
- <a href="#specialty.coding:eRSSpecialty">specialty.coding:eRSSpecialty</a>
- <a href="#specialty.coding:eRSSpecialty.system">specialty.coding:eRSSpecialty.system</a>
- <a href="#location">location</a>
- <a href="#location.identifier.system">location.identifier.system</a>
- <a href="#name">name</a>
- <a href="#telecom">telecom</a>
- <a href="#serviceProvisionCode">serviceProvisionCode</a>
- <a href="#serviceProvisionCode.coding:eRSClinicType">serviceProvisionCode.coding:eRSClinicType</a>
- <a href="#serviceProvisionCode.coding:eRSClinicType.system">serviceProvisionCode.coding:eRSClinicType.system</a>
- <a href="#availableTime">availableTime</a>
- <a href="#endpoint">endpoint</a>
- <a href="#endpoint:nhsMhsPartyKey">endpoint:nhsMhsPartyKey</a>
- <a href="#endpoint:nhsMhsPartyKey.identifier.system">endpoint:nhsMhsPartyKey.identifier.system</a>
- <a href="#endpoint:nhsSpineASID">endpoint:nhsSpineASID</a>
- <a href="#endpoint:nhsSpineASID.identifier.system">endpoint:nhsSpineASID.identifier.system</a>

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|HealthcareService.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 **SHOULD** contain the service identifier e.g. the serviceId from <a href="https://www.directoryofservices.nhs.uk/">Directory of Service</a> or <a href="https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir">e-RS Directory Services</a>

**MAY** contain an ANANA/ODS code. 

```json
"identifier": [
          {
            "use": "official",
            "system": "https://fhir.nhs.uk/Id/ers-service",
            "value": "11021"
          }
        ]
```

 #### Comment

 MUST contain an ANANA/ODS code.

<a name="identifier:ersServiceId"></a>
 ## identifier:ersServiceId

| | |
|----|----|
|Element Id|HealthcareService.identifier:ersServiceId|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|ersServiceId|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 External identifiers for this item.

<a name="identifier:ersServiceId.system"></a>
 ## identifier:ersServiceId.system

| | |
|----|----|
|Element Id|HealthcareService.identifier:ersServiceId.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/ers-service|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:dosServiceId"></a>
 ## identifier:dosServiceId

| | |
|----|----|
|Element Id|HealthcareService.identifier:dosServiceId|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|dosServiceId|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 External identifiers for this item.

<a name="identifier:dosServiceId.system"></a>
 ## identifier:dosServiceId.system

| | |
|----|----|
|Element Id|HealthcareService.identifier:dosServiceId.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://fhir.nhs.uk/Id/dos-service-id|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="providedBy"></a>
 ## providedBy

| | |
|----|----|
|Element Id|HealthcareService.providedBy|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization))|

<br/>

 #### Definition

 It is recommended an *identifier reference* using ODS code is used. 

```json
"providedBy": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RBA"
          },
        "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
    }
```

 #### Comment

 This property is recommended to be the same as the Location's managingOrganization, and if not provided should be interpreted as such. If the Location does not have a managing Organization, then this property should be populated.

<a name="providedBy.identifier.system"></a>
 ## providedBy.identifier.system

| | |
|----|----|
|Element Id|HealthcareService.providedBy.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/ods-organization-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="type"></a>
 ## type

| | |
|----|----|
|Element Id|HealthcareService.type|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ServiceType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/service-type) (Preferred)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Type **SHOULD** be populated. 

```json
"type":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/DoS-ClinicType",
                    "code": "PHARMACY",
                    "display": "Pharmacy"
                }
            ]
        }
    ],
```

or 

```json
"type": [
        {
            "coding": [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/eRS-AppointmentType",
                    "code": "DAY_CASE",
                }
            ]
        }
    ],
```

<a name="type.coding:UKCoreCareSettingType"></a>
 ## type.coding:UKCoreCareSettingType

| | |
|----|----|
|Element Id|HealthcareService.type.coding:UKCoreCareSettingType|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[UKCoreCareSettingType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-CareSettingType) (Preferred)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|UKCoreCareSettingType|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="type.coding:UKCoreCareSettingType.system"></a>
 ## type.coding:UKCoreCareSettingType.system

| | |
|----|----|
|Element Id|HealthcareService.type.coding:UKCoreCareSettingType.system|
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

<a name="type.coding:eRSAppointmentType"></a>
 ## type.coding:eRSAppointmentType

| | |
|----|----|
|Element Id|HealthcareService.type.coding:eRSAppointmentType|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|eRSAppointmentType|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 Appointment type e.g. telephone/video (only applicable and mandatory if Service Type is Appointment Request, not applicable to Service Type of Triage Request)

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="type.coding:eRSAppointmentType.system"></a>
 ## type.coding:eRSAppointmentType.system

| | |
|----|----|
|Element Id|HealthcareService.type.coding:eRSAppointmentType.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/eRS-AppointmentType|
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
|Element Id|HealthcareService.specialty|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[PracticeSettingCodeValueSet](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/c80-practice-codes) (Preferred) <br/>A specialty that a healthcare service may provide. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Specialty **SHOULD** be from the {{link:http://hl7.org/fhir/ValueSet/c80-practice-codes}}
and is the SNOMED equivalent of the [NHS Data Dictionary - Main Specialty and Treatment Function Codes](https://datadictionary.nhs.uk/supporting_information/main_specialty_and_treatment_function_codes_table.html) and FHIR {{pagelink:NHSDataDictionaryClinicalSpecialty}}

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

<a name="specialty.coding:NHSDataDictionarySpecialty"></a>
 ## specialty.coding:NHSDataDictionarySpecialty

| | |
|----|----|
|Element Id|HealthcareService.specialty.coding:NHSDataDictionarySpecialty|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDataDictionaryMainClinicalSpecialty](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDataModelAndDictionary-clinical-specialty) (Required) <br/>NHS Data Dictionary Specialty/Treatment Function Code |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|NHSDataDictionarySpecialty|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="specialty.coding:NHSDataDictionarySpecialty.system"></a>
 ## specialty.coding:NHSDataDictionarySpecialty.system

| | |
|----|----|
|Element Id|HealthcareService.specialty.coding:NHSDataDictionarySpecialty.system|
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

<a name="specialty.coding:SNOMEDPracticeCode"></a>
 ## specialty.coding:SNOMEDPracticeCode

| | |
|----|----|
|Element Id|HealthcareService.specialty.coding:SNOMEDPracticeCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[PracticeSettingCodeValueSet](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/c80-practice-codes) (Preferred) <br/>Specific specialty associated with the agency. |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|SNOMEDPracticeCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="specialty.coding:SNOMEDPracticeCode.system"></a>
 ## specialty.coding:SNOMEDPracticeCode.system

| | |
|----|----|
|Element Id|HealthcareService.specialty.coding:SNOMEDPracticeCode.system|
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

<a name="specialty.coding:eRSSpecialty"></a>
 ## specialty.coding:eRSSpecialty

| | |
|----|----|
|Element Id|HealthcareService.specialty.coding:eRSSpecialty|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDigitaleRSSpecialty](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-eRS-Specialty) (Preferred) <br/>Specific specialty associated with the agency. |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|eRSSpecialty|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="specialty.coding:eRSSpecialty.system"></a>
 ## specialty.coding:eRSSpecialty.system

| | |
|----|----|
|Element Id|HealthcareService.specialty.coding:eRSSpecialty.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/eRS-Specialty|
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
|Element Id|HealthcareService.location|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalLocation](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Location))|

<br/>

 #### Definition

 Reference to a location. ODS codes may be used, however this may differ from Directory of Services and so DoS addresses are preferred.

```json
 "location":  [
        {
            "reference": "urn:uuid:8a5d7d67-64fb-44ec-9802-2dc214bb3dcb"
        }
    ],
```

or 

```json
"location": [
        {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-site-code",
                "value": "R6901"
            }
        }
    ],
```

 #### Constraints 

- **nhsd-8** (*ERROR*) location - An identifier reference or resource reference must be provided

<a name="location.identifier.system"></a>
 ## location.identifier.system

| | |
|----|----|
|Element Id|HealthcareService.location.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/ods-site-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="name"></a>
 ## name

| | |
|----|----|
|Element Id|HealthcareService.name|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 Name of the clinic or service.

```json
 "name": "SOMERSET BOWEL CANCER SCREENING CENTRE",
```

<a name="telecom"></a>
 ## telecom

| | |
|----|----|
|Element Id|HealthcareService.telecom|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[ContactPoint](https://www.hl7.org/fhir/datatypes.html#ContactPoint)|

<br/>

 #### Definition

 Contact details for the clinic or service. 

```json
   "telecom": [
    {
      "system": "phone",
      "value": "0113 922 4984",
      "use": "work"
    },
    {
      "system": "email",
      "value": "directaddress@example.com",
      "use": "work"
    }
  ],
```

 #### Comment

 If this is empty, then refer to the location's contacts.

<a name="serviceProvisionCode"></a>
 ## serviceProvisionCode

| | |
|----|----|
|Element Id|HealthcareService.serviceProvisionCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ServiceProvisionConditions](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/service-provision-conditions) (Example) <br/>The code(s) that detail the conditions under which the healthcare service is available/offered. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 The code(s) that detail the conditions under which the healthcare service is available/offered.

 #### Comment

 The provision means being commissioned by, contractually obliged or financially sourced. Types of costings that may apply to this healthcare service, such if the service may be available for free, some discounts available, or fees apply.

<a name="serviceProvisionCode.coding:eRSClinicType"></a>
 ## serviceProvisionCode.coding:eRSClinicType

| | |
|----|----|
|Element Id|HealthcareService.serviceProvisionCode.coding:eRSClinicType|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ERSClinicType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-eRS-ClinicType) (Required)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|eRSClinicType|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="serviceProvisionCode.coding:eRSClinicType.system"></a>
 ## serviceProvisionCode.coding:eRSClinicType.system

| | |
|----|----|
|Element Id|HealthcareService.serviceProvisionCode.coding:eRSClinicType.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/NHSDigital-ClinicType|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="availableTime"></a>
 ## availableTime

| | |
|----|----|
|Element Id|HealthcareService.availableTime|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 Opening times for the clinic or service. 


```json
"availableTime": [
    {
      "daysOfWeek": [
        "wed"
      ],
      "allDay": true
    },
    {
      "daysOfWeek": [
        "mon",
        "tue",
        "wed",
        "thu"
      ],
      "availableStartTime": "08:30:00",
      "availableEndTime": "05:30:00"
    },
    {
      "daysOfWeek": [
        "sat",
        "fri"
      ],
      "availableStartTime": "09:30:00",
      "availableEndTime": "04:30:00"
    }
  ],
```

 #### Comment

 More detailed availability information may be provided in associated Schedule/Slot resources.

<a name="endpoint"></a>
 ## endpoint

| | |
|----|----|
|Element Id|HealthcareService.endpoint|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *identifier.system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Endpoint](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Endpoint))|

<br/>

 #### Definition

 Technical endpoints providing access to services operated for the specific healthcare services defined at this resource.

Endpoint identifiers to be used with the HealthcareService. Endpoints can be resolved using the SDS API

```json
"endpoint": [
        {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/nhsSpineASID", // or https://fhir.nhs.uk/Id/nhsMhsPartyKey
                "value": "999900000041"
            }
        }
    ]
```

<a name="endpoint:nhsMhsPartyKey"></a>
 ## endpoint:nhsMhsPartyKey

| | |
|----|----|
|Element Id|HealthcareService.endpoint:nhsMhsPartyKey|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|nhsMhsPartyKey|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Endpoint](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Endpoint))|

<br/>

 #### Definition

 Technical endpoints providing access to services operated for the specific healthcare services defined at this resource.

<a name="endpoint:nhsMhsPartyKey.identifier.system"></a>
 ## endpoint:nhsMhsPartyKey.identifier.system

| | |
|----|----|
|Element Id|HealthcareService.endpoint:nhsMhsPartyKey.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/Id/nhsMhsPartyKey|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="endpoint:nhsSpineASID"></a>
 ## endpoint:nhsSpineASID

| | |
|----|----|
|Element Id|HealthcareService.endpoint:nhsSpineASID|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|nhsSpineASID|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Endpoint](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Endpoint))|

<br/>

 #### Definition

 Technical endpoints providing access to services operated for the specific healthcare services defined at this resource.

<a name="endpoint:nhsSpineASID.identifier.system"></a>
 ## endpoint:nhsSpineASID.identifier.system

| | |
|----|----|
|Element Id|HealthcareService.endpoint:nhsSpineASID.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/Id/nhsSpineASID|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.