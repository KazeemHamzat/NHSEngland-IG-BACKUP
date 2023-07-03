## {{page-title}}


| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest) | | draft |

<br>

### Conformance Rules


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
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
       
        <div id="Combined" role="tabpanel" class="tab-pane active">
            <br>
            with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest}} 
          <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, combined}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
        
  {{tree: https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, diff}}
        </div>
<div id="Examples"  class="tab-pane">

None defined at present
<br/>

</div>

### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
```

<br/>

 #### Definition

 A record of a request for service such as diagnostic investigations, treatments, or operations to be performed.

 #### Constraints 

- **prr-1** (*ERROR*) orderDetail SHALL only be present if code is present


- <a href="#extension:ERSAdviceAndGuidance">extension:ERSAdviceAndGuidance</a>
- <a href="#extension:ERSServiceRequestState">extension:ERSServiceRequestState</a>
- <a href="#extension:portalLink">extension:portalLink</a>
- <a href="#extension:serviceRequestPriority">extension:serviceRequestPriority</a>
- <a href="#identifier">identifier</a>
- <a href="#identifier:UBRN">identifier:UBRN</a>
- <a href="#identifier:UBRN.system">identifier:UBRN.system</a>
- <a href="#basedOn">basedOn</a>
- <a href="#basedOn.identifier">basedOn.identifier</a>
- <a href="#category">category</a>
- <a href="#category.coding.system">category.coding.system</a>
- <a href="#priority">priority</a>
- <a href="#code">code</a>
- <a href="#code.coding:SNOMEDProcedureCode">code.coding:SNOMEDProcedureCode</a>
- <a href="#code.coding:SNOMEDProcedureCode.system">code.coding:SNOMEDProcedureCode.system</a>
- <a href="#subject">subject</a>
- <a href="#subject.identifier.system">subject.identifier.system</a>
- <a href="#authoredOn">authoredOn</a>
- <a href="#requester">requester</a>
- <a href="#performerType">performerType</a>
- <a href="#performerType.coding:treatmentFunctionCodes">performerType.coding:treatmentFunctionCodes</a>
- <a href="#performerType.coding:treatmentFunctionCodes.system">performerType.coding:treatmentFunctionCodes.system</a>
- <a href="#performerType.coding:eRSSpecialty">performerType.coding:eRSSpecialty</a>
- <a href="#performerType.coding:eRSSpecialty.system">performerType.coding:eRSSpecialty.system</a>
- <a href="#performer">performer</a>
- <a href="#performer.identifier">performer.identifier</a>
- <a href="#reasonCode">reasonCode</a>
- <a href="#supportingInfo">supportingInfo</a>
- <a href="#note">note</a>

<a name="extension:ERSAdviceAndGuidance"></a>
 ## extension:ERSAdviceAndGuidance

| | |
|----|----|
|Element Id|ServiceRequest.extension:ERSAdviceAndGuidance|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|ERSAdviceAndGuidance|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionERSAdviceAndGuidance](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-England-ERSReferral))|

<br/>

 #### Definition

 ```json
  "extension": [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-ERSReferral",
            "extension": [
                {
                    "url": "sourceSystem",
                    "valueCode": "ers"
                },
                {
                    "url": "status",
                    "valueCode": "unbooked"
                }
            ]
        },
```

<a name="extension:ERSServiceRequestState"></a>
 ## extension:ERSServiceRequestState

| | |
|----|----|
|Element Id|ServiceRequest.extension:ERSServiceRequestState|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|ERSServiceRequestState|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionNHSDigitaleRSReferralState](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-England-ERSServiceRequestState))|

<br/>

 #### Definition

 e-RS representation of the state of the referral

```json
"extension": [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-ERS-Referral",
            "extension": [
                {
                    "url": "sourceSystem",
                    "valueCode": "ers"
                },
                {
                    "url": "status",
                    "valueCode": "unbooked"
                }
            ]
        }
    ],
```

<a name="extension:portalLink"></a>
 ## extension:portalLink

| | |
|----|----|
|Element Id|ServiceRequest.extension:portalLink|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|portalLink|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionPortalLink](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-Portal-Link))|

<br/>

 #### Definition

 Deep Link into the specific landing page in MYR

```json
"extension": [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-Portal-Link",
            "valueUrl": "https://virtual.nhs.uk/MyPatientRecords"
        }
    ],
```

<a name="extension:serviceRequestPriority"></a>
 ## extension:serviceRequestPriority

| | |
|----|----|
|Element Id|ServiceRequest.extension:serviceRequestPriority|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|serviceRequestPriority|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionServiceRequestPriority](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-ServiceRequest-Priority))|

<br/>

 #### Definition

 Optional Extension Element - found in all resources.

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|ServiceRequest.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 Identifiers assigned to this order instance by the orderer and/or the receiver and/or order fulfiller.

```json
"identifier": [
                    {
                        "system": "https://fhir.nhs.uk/Id/UBRN",
                        "value": "111111111112"
                    }
                ],
```

 #### Comment

 The identifier.type element is used to distinguish between the identifiers assigned by the orderer (known as the 'Placer' in HL7 v2) and the producer of the observations in response to the order (known as the 'Filler' in HL7 v2).  For further discussion and examples see the resource notes section below.

<a name="identifier:UBRN"></a>
 ## identifier:UBRN

| | |
|----|----|
|Element Id|ServiceRequest.identifier:UBRN|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|UBRN|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 Unique Booking Reference Number
(12 digit number used as an internal and external identifier of the referral), known as "Booking Reference" Patient side

 #### Comment

 The identifier.type element is used to distinguish between the identifiers assigned by the orderer (known as the 'Placer' in HL7 v2) and the producer of the observations in response to the order (known as the 'Filler' in HL7 v2).  For further discussion and examples see the resource notes section below.

<a name="identifier:UBRN.system"></a>
 ## identifier:UBRN.system

| | |
|----|----|
|Element Id|ServiceRequest.identifier:UBRN.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/UBRN|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="basedOn"></a>
 ## basedOn

| | |
|----|----|
|Element Id|ServiceRequest.basedOn|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([CarePlan](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/CarePlan) [MedicationRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/MedicationRequest) [ServiceRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/ServiceRequest))|

<br/>

 #### Definition

 Plan/proposal/order fulfilled by this request.

<a name="basedOn.identifier"></a>
 ## basedOn.identifier

| | |
|----|----|
|Element Id|ServiceRequest.basedOn.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier for the target resource. This is used when there is no way to reference the other resource directly, either because the entity it represents is not available through a FHIR server, or because there is no way for the author of the resource to convert a known identifier to an actual location. There is no requirement that a Reference.identifier point to something that is actually exposed as a FHIR instance, but it SHALL point to a business concept that would be expected to be exposed as a FHIR instance, and that instance would need to be of a FHIR resource type allowed by the reference.

 #### Comment

 When an identifier is provided in place of a reference, any system processing the reference will only be able to resolve the identifier to a reference if it understands the business context in which the identifier is used. Sometimes this is global (e.g. a national identifier) but often it is not. For this reason, none of the useful mechanisms described for working with references (e.g. chaining, includes) are possible, nor should servers be expected to be able resolve the reference. Servers may accept an identifier based reference untouched, resolve it, and/or reject it - see CapabilityStatement.rest.resource.referencePolicy.   When both an identifier and a literal reference are provided, the literal reference is preferred. Applications processing the resource are allowed - but not required - to check that the identifier matches the literal reference  Applications converting a logical reference to a literal reference may choose to leave the logical reference present, or remove it.  Reference is intended to point to a structure that can potentially be expressed as a FHIR resource, though there is no need for it to exist as an actual FHIR resource instance - except in as much as an application wishes to actual find the target of the reference. The content referred to be the identifier must meet the logical constraints implied by any limitations on what resource types are permitted for the reference.  For example, it would not be legitimate to send the identifier for a drug prescription if the type were Reference(Observation|DiagnosticReport).  One of the use-cases for Reference.identifier is the situation where no FHIR representation exists (where the type is Reference (Any).

<a name="category"></a>
 ## category

| | |
|----|----|
|Element Id|ServiceRequest.category|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ServiceRequestCategoryCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/servicerequest-category) (Example) <br/>Classification of the requested service. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 A code that classifies the service for searching, sorting and display purposes (e.g. "Surgical Procedure").

At present the only code in use is Patient Referral

```json
 "category": [
        {
            "coding": [
                {
                    "system": "http://snomed.info/sct",
                    "code": "3457005",
                    "display": "Patient referral"
                }
            ]
        }
    ],
```

 #### Requirements

 Used for filtering what service request are retrieved and displayed.

 #### Comment

 There may be multiple axis of categorization depending on the context or use case for retrieving or displaying the resource.  The level of granularity is defined by the category concepts in the value set.

<a name="category.coding.system"></a>
 ## category.coding.system

| | |
|----|----|
|Element Id|ServiceRequest.category.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://snomed.info/sct|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="priority"></a>
 ## priority

| | |
|----|----|
|Element Id|ServiceRequest.priority|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[RequestPriority](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/request-priority&#124;4.0.1) (Required) <br/>Identifies the level of importance to be assigned to actioning the request. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 Request Priority Code 

Code for the priority of the referral set by the Referring Clinician

```json
 "priority": "routine",
```

<a name="code"></a>
 ## code

| | |
|----|----|
|Element Id|ServiceRequest.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[UKCoreProcedureCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-ProcedureCode) (Preferred) <br/>A set of codes that define a procedure or a procedure with explicit context. Selected from the SNOMED CT UK coding system. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 A code that identifies a particular service (i.e., procedure, diagnostic investigation, or panel of investigations) that have been requested.

Ideally this should be a child code of the ServiceRequest.category

 #### Comment

 Many laboratory and radiology procedure codes embed the specimen/organ system in the test order name, for example,  serum or serum/plasma glucose, or a chest x-ray. The specimen might not be recorded separately from the test code.

<a name="code.coding:SNOMEDProcedureCode"></a>
 ## code.coding:SNOMEDProcedureCode

| | |
|----|----|
|Element Id|ServiceRequest.code.coding:SNOMEDProcedureCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|SNOMEDProcedureCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="code.coding:SNOMEDProcedureCode.system"></a>
 ## code.coding:SNOMEDProcedureCode.system

| | |
|----|----|
|Element Id|ServiceRequest.code.coding:SNOMEDProcedureCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://snomed.info/sct|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="subject"></a>
 ## subject

| | |
|----|----|
|Element Id|ServiceRequest.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient))|

<br/>

 #### Definition

 On whom or what the service is to be performed. This is usually a human patient, but can also be requested on animals, groups of humans or animals, devices such as dialysis machines, or even locations (typically for environmental scans).

```json
"subject": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9999998887"
        }
    },
```

 #### Constraints 

- **patient-reference** (*ERROR*) An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) NHS Number must be in the English and Welsh NHS Number range or length of the number is wrong.

<a name="subject.identifier.system"></a>
 ## subject.identifier.system

| | |
|----|----|
|Element Id|ServiceRequest.subject.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/nhs-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="authoredOn"></a>
 ## authoredOn

| | |
|----|----|
|Element Id|ServiceRequest.authoredOn|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 Date the referral was initiated in e-RS

```json
"authoredOn": "2022-01-11T16:40:00+00:00",
```

<a name="requester"></a>
 ## requester

| | |
|----|----|
|Element Id|ServiceRequest.requester|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitionerRoleMinimal](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-Minimal))<br/> Aggregation - [contained](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 Who is created the Request or the Event. In NHSDigital API's this **SHOULD** always be a PractitionerRole role reference.

```json
 "requester": {
        "reference": "#requester"
    },
```

This will reference a `contained` PractitionerRole (note: this resource only contains limited user metadata such as ODS Code, professional code and SDS User Profile Id). This resource should not hold data which is held in SDS, only enough information to identify the SDS Entry,

```json
{
    "resourceType": "ServiceRequest",
    "id": "bd1ca5c4-ff49-4f2a-9db4-f5dda0112084",
    "meta": {
        "lastUpdated": "2016-07-11T11:07:22+00:00"
    },
    "contained": [
        {
            "resourceType": "PractitionerRole",
            "id": "requester",
            "practitioner": {
                "identifier": {
                    "system": "https://fhir.hl7.org.uk/Id/gmp-number",
                    "value": "G8123456"
                },
                "display": "DR AA BHATIA"
            },
            "organization": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "C81007"
                },
                "display": "VERNON STREET MEDICAL CTR"
            },
        }
    ],
    "requester": {
        "reference": "#requester"
    },
```

**e-RS**

The contained PractitionerRole must contain

- SDS User ID of the Referrer in `practitioner`
- ODS Code of the Referring Organisation in `organization`

 #### Comment

 This not the dispatcher, but rather who is the authorizer.  This element is not intended to handle delegation which would generally be managed through the Provenance resource.

<a name="performerType"></a>
 ## performerType

| | |
|----|----|
|Element Id|ServiceRequest.performerType|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ParticipantRoles](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/participant-role) (Example) <br/>Indicates specific responsibility of an individual within the care team, such as "Primary physician", "Team coordinator", "Caregiver", etc. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 **ERS**

Specialty used to search for the shortlisted service(s) (if one was used)


```json
"performerType": {
        "coding": [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/eRS-Specialty",
                "code": "GENERAL_MEDICINE"
            }
        ]
    },
```

```json
"performerType": {
                    "coding": [
                        {
                            "display": "Dermatology"
                        }
                    ]
                }
```

 #### Comment

 This is a  role, not  a participation type.  In other words, does not describe the task but describes the capacity.  For example, “compounding pharmacy”, “psychiatrist” or “internal referral”.

<a name="performerType.coding:treatmentFunctionCodes"></a>
 ## performerType.coding:treatmentFunctionCodes

| | |
|----|----|
|Element Id|ServiceRequest.performerType.coding:treatmentFunctionCodes|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDataDictionaryTreatmentFunctionCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDataModelAndDictionary-treatment-function) (Required)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|treatmentFunctionCodes|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="performerType.coding:treatmentFunctionCodes.system"></a>
 ## performerType.coding:treatmentFunctionCodes.system

| | |
|----|----|
|Element Id|ServiceRequest.performerType.coding:treatmentFunctionCodes.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/NHSDataModelAndDictionary-treatment-function|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="performerType.coding:eRSSpecialty"></a>
 ## performerType.coding:eRSSpecialty

| | |
|----|----|
|Element Id|ServiceRequest.performerType.coding:eRSSpecialty|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDigitaleRSSpecialty](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-eRS-Specialty) (Required)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|eRSSpecialty|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="performerType.coding:eRSSpecialty.system"></a>
 ## performerType.coding:eRSSpecialty.system

| | |
|----|----|
|Element Id|ServiceRequest.performerType.coding:eRSSpecialty.system|
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

<a name="performer"></a>
 ## performer

| | |
|----|----|
|Element Id|ServiceRequest.performer|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([UKCoreCareTeam](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-CareTeam) [UKCoreDevice](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device) [UKCoreHealthcareService](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-HealthcareService) [UKCoreOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization) [UKCorePatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient) [UKCorePractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner) [UKCorePractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole) [UKCoreRelatedPerson](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson))|

<br/>

 #### Definition

 The desired performer for doing the requested service.  For example, the surgeon, dermatopathologist, endoscopist, etc.

 #### Comment

 If multiple performers are present, it is interpreted as a list of *alternative* performers without any preference regardless of order.  If order of preference is needed use the [request-performerOrder extension](http://hl7.org/fhir/R4/extension-request-performerorder.html).  Use CareTeam to represent a group of performers (for example, Practitioner A *and* Practitioner B).

<a name="performer.identifier"></a>
 ## performer.identifier

| | |
|----|----|
|Element Id|ServiceRequest.performer.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier for the target resource. This is used when there is no way to reference the other resource directly, either because the entity it represents is not available through a FHIR server, or because there is no way for the author of the resource to convert a known identifier to an actual location. There is no requirement that a Reference.identifier point to something that is actually exposed as a FHIR instance, but it SHALL point to a business concept that would be expected to be exposed as a FHIR instance, and that instance would need to be of a FHIR resource type allowed by the reference.

 #### Comment

 When an identifier is provided in place of a reference, any system processing the reference will only be able to resolve the identifier to a reference if it understands the business context in which the identifier is used. Sometimes this is global (e.g. a national identifier) but often it is not. For this reason, none of the useful mechanisms described for working with references (e.g. chaining, includes) are possible, nor should servers be expected to be able resolve the reference. Servers may accept an identifier based reference untouched, resolve it, and/or reject it - see CapabilityStatement.rest.resource.referencePolicy.   When both an identifier and a literal reference are provided, the literal reference is preferred. Applications processing the resource are allowed - but not required - to check that the identifier matches the literal reference  Applications converting a logical reference to a literal reference may choose to leave the logical reference present, or remove it.  Reference is intended to point to a structure that can potentially be expressed as a FHIR resource, though there is no need for it to exist as an actual FHIR resource instance - except in as much as an application wishes to actual find the target of the reference. The content referred to be the identifier must meet the logical constraints implied by any limitations on what resource types are permitted for the reference.  For example, it would not be legitimate to send the identifier for a drug prescription if the type were Reference(Observation|DiagnosticReport).  One of the use-cases for Reference.identifier is the situation where no FHIR representation exists (where the type is Reference (Any).

<a name="reasonCode"></a>
 ## reasonCode

| | |
|----|----|
|Element Id|ServiceRequest.reasonCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[UKCoreServiceRequestReasonCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-ServiceRequestReasonCode) (Extensible) <br/>A set of codes that define a reason for a service request. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 An explanation or justification for why this service is being requested in coded or textual form.   This is often for billing purposes.  May relate to the resources referred to in `supportingInfo`.

 #### Comment

 This element represents why the referral is being made and may be used to decide how the service will be performed, or even if it will be performed at all.   Use `CodeableConcept.text` element if the data is free (uncoded) text as shown in the [CT Scan example](https://fhir.nhs.uk/R4/servicerequest-example-di.html).

<a name="supportingInfo"></a>
 ## supportingInfo

| | |
|----|----|
|Element Id|ServiceRequest.supportingInfo|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Resource](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Resource) [NHSDigitalDocumentReference](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-DocumentReference))<br/> Aggregation - [referenced](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 Additional clinical information about the patient or specimen that may influence the services or their interpretations.     This information includes diagnosis, clinical findings and other observations.  In laboratory ordering these are typically referred to as "ask at order entry questions (AOEs)".  This includes observations explicitly requested by the producer (filler) to provide context or supporting information needed to complete the order. For example,  reporting the amount of inspired oxygen for blood gas measurements.

```json
"supportingInfo": [
        {
            "type" : "DocumentReference",
            "reference": "DocumentReference/5da894e0-a57e-43e9-a1a1-e283a484003c"
        },
        {
            "type" : "QuestionnaireResponse",
            "reference" : "QuestionnaireResponse/d9d4cf80-3f9d-4435-9f3b-e6efb09ad654"
        }
    ],
```

 #### Comment

 To represent information about how the services are to be delivered use the `instructions` element.

<a name="note"></a>
 ## note

| | |
|----|----|
|Element Id|ServiceRequest.note|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Annotation](https://www.hl7.org/fhir/datatypes.html#Annotation)|

<br/>

 #### Definition

 Any other notes and comments made about the service request. For example, internal billing notes.

 #### Comment

 For systems that do not have structured annotations, they can simply communicate a single annotation with no author or time.  This element may need to be included in narrative because of the potential for modifying information.  *Annotations SHOULD NOT* be used to communicate "modifying" information that could be computable. (This is a SHOULD because enforcing user behavior is nearly impossible).

```json
"note": [
        {
            "text": "Please advise me on this patient who ...(information about patient)"
        }
    ]
```