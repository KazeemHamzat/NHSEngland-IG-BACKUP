## NHSDigital-Encounter

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Experimental. This page is for illustration of a concept</div>

  | Profile url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Encounter](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Encounter) | {{pagelink:Administration}} | draft |


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
  with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Encounter, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
 from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Encounter, diff}}
        </div>
<div id="Examples"  class="tab-pane">

- {{pagelink:InpatientEncounter}}

</div>
</div>

---


@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/England-Encounter'
for differential.element
select id,min, definition
```

<br/>

 #### Definition

 An interaction between a patient and healthcare provider(s) for the purpose of providing healthcare service(s) or assessing the health status of a patient.


- <a href="#identifier">identifier</a>
- <a href="#subject">subject</a>
- <a href="#participant">participant</a>
- <a href="#participant.individual">participant.individual</a>
- <a href="#reasonCode">reasonCode</a>

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Encounter.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 In ITK HL7v2 this is PV1.19 Visit Number .

Identifier(s) by which this encounter is known.

<a name="subject"></a>
 ## subject

| | |
|----|----|
|Element Id|Encounter.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Group](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Group) [UKCorePatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient))|

<br/>

 #### Definition

 The patient or group present at the encounter.

 #### Comment

 While the encounter is always about the patient, the patient might not actually be known in all contexts of use, and there may be a group of patients that could be anonymous (such as in a group therapy for Alcoholics Anonymous - where the recording of the encounter could be used for billing on the number of people/staff and not important to the context of the specific patients) or alternately in veterinary care a herd of sheep receiving treatment (where the animals are not individually tracked).

 #### Constraints 

- **patient-reference** (*WARNING*) subject - An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="participant"></a>
 ## participant

| | |
|----|----|
|Element Id|Encounter.participant|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 In HL7v2 this is PV1.7 Attending Doctor, PV1.8 Referring Doctor and PV1.9 Consulting Doctor

The list of people responsible for providing the service.

<a name="participant.individual"></a>
 ## participant.individual

| | |
|----|----|
|Element Id|Encounter.participant.individual|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([UKCorePractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner) [UKCorePractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole) [UKCoreRelatedPerson](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson))|

<br/>

 #### Definition

 Persons involved in the encounter other than the patient.

<a name="reasonCode"></a>
 ## reasonCode

| | |
|----|----|
|Element Id|Encounter.reasonCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[EncounterReasonCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/encounter-reason) (Preferred) <br/>Reason why the encounter takes place. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Reason the encounter takes place, expressed as a code. For admissions, this can be used for a coded admission diagnosis.

 #### Comment

 For systems that need to know which was the primary diagnosis, these will be marked with the standard extension primaryDiagnosis (which is a sequence value rather than a flag, 1 = primary diagnosis).
