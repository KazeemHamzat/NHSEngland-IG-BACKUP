## {{page-title}}


| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Appointment](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Appointment) | {{pagelink:Administration}} | trial-use |

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
    
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Appointment, combined}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
        
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Appointment, diff}}
        </div>
<div id="Examples"  class="tab-pane">

None defined at present
<br/>

</div>

### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Appointment' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
``` 

<br/>

<br/>

 #### Definition

 A booking of a healthcare event among patient(s), practitioner(s), related person(s) and/or device(s) for a specific date/time. This may result in one or more Encounter(s).

 #### Constraints 

- **app-2** (*ERROR*) Either start and end are specified, or neither
- **app-3** (*ERROR*) Only proposed or cancelled appointments can be missing start/end dates
- **app-4** (*ERROR*) Cancellation reason is only used for appointments that have been cancelled, or no-show

<br/>



- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#serviceCategory:NHSDataDictionaryTreatmentFunction">serviceCategory:NHSDataDictionaryTreatmentFunction</a>
- <a href="#serviceCategory:NHSDataDictionaryTreatmentFunction.coding.system">serviceCategory:NHSDataDictionaryTreatmentFunction.coding.system</a>
- <a href="#serviceCategory:eRSClinicType">serviceCategory:eRSClinicType</a>
- <a href="#serviceCategory:eRSClinicType.coding.system">serviceCategory:eRSClinicType.coding.system</a>
- <a href="#reasonCode">reasonCode</a>
- <a href="#start">start</a>
- <a href="#end">end</a>
- <a href="#slot">slot</a>
- <a href="#slot:alternativeSlot">slot:alternativeSlot</a>
- <a href="#slot:alternativeSlot.identifier.system">slot:alternativeSlot.identifier.system</a>
- <a href="#basedOn">basedOn</a>
- <a href="#basedOn.identifier">basedOn.identifier</a>
- <a href="#participant">participant</a>
- <a href="#participant.actor">participant.actor</a>

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Appointment.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 This records identifiers associated with this appointment concern that are defined by business processes and/or used to refer to it when a direct URL reference to the resource itself is not appropriate (e.g. in CDA documents, or in written / printed documentation).

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|Appointment.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[AppointmentStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/appointmentstatus&#124;4.0.1) (Required) <br/>The free/busy status of an appointment. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 The overall status of the Appointment. Each of the participants has their own participation status which indicates their involvement in the process, however this status indicates the shared status.

**e-RS**

Will default to `booked`

 #### Comment

 If the Appointment's status is "cancelled" then all participants are expected to have their calendars released for the appointment period, and as such any Slots that were marked as BUSY can be re-set to FREE.  This element is labelled as a modifier because the status contains the code entered-in-error that mark the Appointment as not currently valid.

<a name="serviceCategory:NHSDataDictionaryTreatmentFunction"></a>
 ## serviceCategory:NHSDataDictionaryTreatmentFunction

| | |
|----|----|
|Element Id|Appointment.serviceCategory:NHSDataDictionaryTreatmentFunction|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ServiceCategory](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/service-category) (Example)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|NHSDataDictionaryTreatmentFunction|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 A broad categorisation of the service that is to be performed during this appointment.

<a name="serviceCategory:NHSDataDictionaryTreatmentFunction.coding.system"></a>
 ## serviceCategory:NHSDataDictionaryTreatmentFunction.coding.system

| | |
|----|----|
|Element Id|Appointment.serviceCategory:NHSDataDictionaryTreatmentFunction.coding.system|
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

<a name="serviceCategory:eRSClinicType"></a>
 ## serviceCategory:eRSClinicType

| | |
|----|----|
|Element Id|Appointment.serviceCategory:eRSClinicType|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ServiceCategory](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/service-category) (Example)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|eRSClinicType|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 A broad categorisation of the service that is to be performed during this appointment.

<a name="serviceCategory:eRSClinicType.coding.system"></a>
 ## serviceCategory:eRSClinicType.coding.system

| | |
|----|----|
|Element Id|Appointment.serviceCategory:eRSClinicType.coding.system|
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

<a name="reasonCode"></a>
 ## reasonCode

| | |
|----|----|
|Element Id|Appointment.reasonCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[EncounterReasonCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/encounter-reason) (Preferred) <br/>The Reason for the appointment to take place. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 The coded reason that this appointment is being scheduled. This is more clinical than administrative.

<a name="start"></a>
 ## start

| | |
|----|----|
|Element Id|Appointment.start|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[instant](https://www.hl7.org/fhir/datatypes.html#instant)|

<br/>

 #### Definition

 Date time of the current appointment booking (if there is a current appointment booking to a Directly Bookable Service)

```json
 "start": "2021-06-13T12:30:00+00:00",
```

<a name="end"></a>
 ## end

| | |
|----|----|
|Element Id|Appointment.end|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[instant](https://www.hl7.org/fhir/datatypes.html#instant)|

<br/>

 #### Definition

 Date/Time that the appointment is to conclude.

```json
"end": "2021-06-13T12:45:00+00:00",
```

<a name="slot"></a>
 ## slot

| | |
|----|----|
|Element Id|Appointment.slot|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *identifier.system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([UKCoreSlot](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot))|

<br/>

 #### Definition

 The slots from the participants' schedules that will be filled by the appointment.

<a name="slot:alternativeSlot"></a>
 ## slot:alternativeSlot

| | |
|----|----|
|Element Id|Appointment.slot:alternativeSlot|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|alternativeSlot|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([UKCoreSlot](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot))|

<br/>

 #### Definition

 ```json
 "slot": [
                    {
                        "identifier": {
                            "system": "https://fhir.nhs.uk/CodeSystem/unique-slot-reference-number",
                            "value": "USRN-12000001"
                        }
                    }
                ],
```

<a name="slot:alternativeSlot.identifier.system"></a>
 ## slot:alternativeSlot.identifier.system

| | |
|----|----|
|Element Id|Appointment.slot:alternativeSlot.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/unique-slot-reference-number|
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
|Element Id|Appointment.basedOn|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([ServiceRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/ServiceRequest))|

<br/>

 #### Definition

 The service request this appointment is allocated to assess (e.g. incoming referral or procedure request).

```json
"basedOn": [
                    {
                        "reference": "https://server.fire.ly/ServiceRequest/6c2a1f9b-2517-419d-9099-591ba63f176c"
                    }
                ],
```

<a name="basedOn.identifier"></a>
 ## basedOn.identifier

| | |
|----|----|
|Element Id|Appointment.basedOn.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier for the target resource. This is used when there is no way to reference the other resource directly, either because the entity it represents is not available through a FHIR server, or because there is no way for the author of the resource to convert a known identifier to an actual location. There is no requirement that a Reference.identifier point to something that is actually exposed as a FHIR instance, but it SHALL point to a business concept that would be expected to be exposed as a FHIR instance, and that instance would need to be of a FHIR resource type allowed by the reference.

 #### Comment

 When an identifier is provided in place of a reference, any system processing the reference will only be able to resolve the identifier to a reference if it understands the business context in which the identifier is used. Sometimes this is global (e.g. a national identifier) but often it is not. For this reason, none of the useful mechanisms described for working with references (e.g. chaining, includes) are possible, nor should servers be expected to be able resolve the reference. Servers may accept an identifier based reference untouched, resolve it, and/or reject it - see CapabilityStatement.rest.resource.referencePolicy.   When both an identifier and a literal reference are provided, the literal reference is preferred. Applications processing the resource are allowed - but not required - to check that the identifier matches the literal reference  Applications converting a logical reference to a literal reference may choose to leave the logical reference present, or remove it.  Reference is intended to point to a structure that can potentially be expressed as a FHIR resource, though there is no need for it to exist as an actual FHIR resource instance - except in as much as an application wishes to actual find the target of the reference. The content referred to be the identifier must meet the logical constraints implied by any limitations on what resource types are permitted for the reference.  For example, it would not be legitimate to send the identifier for a drug prescription if the type were Reference(Observation|DiagnosticReport).  One of the use-cases for Reference.identifier is the situation where no FHIR representation exists (where the type is Reference (Any).

<a name="participant"></a>
 ## participant

| | |
|----|----|
|Element Id|Appointment.participant|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 List of participants involved in the appointment.

This should include a Patient and a HealthcareService

```json
 "participant": [
                    {
                        "actor": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/ers-service",
                                "value": "11002"
                            }
                        },
                        "status": "accepted"
                    },
                    {
                        "actor": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/nhs-number",
                                "value": "9912003888"
                            }
                        },
                        "status": "accepted"
                    }
                ]
```

 #### Constraints 

- **app-1** (*ERROR*) Either the type or actor on the participant SHALL be specified

<a name="participant.actor"></a>
 ## participant.actor

| | |
|----|----|
|Element Id|Appointment.participant.actor|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalHealthcareService](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService) [NHSDigitalPractitionerRoleMinimal](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-Minimal) [NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient) [NHSDigitalLocation](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Location) [NHSDigitalPractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner))<br/> Aggregation - [contained](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)<br/> Aggregation - [referenced](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 A Person, Location/HealthcareService or Device that is participating in the appointment.

 #### Constraints 

- **participant** (*ERROR*) An identifier reference or resource reference must be provided