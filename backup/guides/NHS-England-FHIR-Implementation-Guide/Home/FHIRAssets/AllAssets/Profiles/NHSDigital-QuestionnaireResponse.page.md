### NHSDigital-QuestionnaireResponse

 <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Experimental. This page is for illustration of a concept</div>

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-QuestionnaireResponse](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-QuestionnaireResponse) | | trial-use |

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
       with {{link:http://hl7.org/fhir/StructureDefinition/QuestionnaireResponse}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-QuestionnaireResponse, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
         from {{link:http://hl7.org/fhir/StructureDefinition/QuestionnaireResponse}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-QuestionnaireResponse, diff}}
        </div>
<div id="Examples"  class="tab-pane">

- {{pagelink:COVID19VaccinationExemption}}

</div>
</div>

<br/>

 #### Definition

 A structured set of questions and their answers. The questions are ordered and grouped into coherent subsets, corresponding to the structure of the grouping of the questionnaire being responded to.

 #### Comment

 The QuestionnaireResponse contains enough information about the questions asked and their organization that it can be interpreted somewhat independently from the Questionnaire it is based on.  I.e. You don't need access to the Questionnaire in order to extract basic information from a QuestionnaireResponse.


- <a href="#identifier">identifier</a>
- <a href="#questionnaire">questionnaire</a>
- <a href="#status">status</a>
- <a href="#subject">subject</a>
- <a href="#subject.identifier.system">subject.identifier.system</a>
- <a href="#subject.identifier.value">subject.identifier.value</a>
- <a href="#subject.display">subject.display</a>
- <a href="#authored">authored</a>
- <a href="#author">author</a>
- <a href="#author.identifier.system">author.identifier.system</a>
- <a href="#author.identifier.value">author.identifier.value</a>
- <a href="#author.display">author.display</a>
- <a href="#source">source</a>
- <a href="#source.identifier">source.identifier</a>
- <a href="#source.display">source.display</a>
- <a href="#item">item</a>

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|QuestionnaireResponse.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 A business identifier assigned to a particular completed (or partially completed) questionnaire.

 #### Requirements

 Used for tracking, registration and other business purposes.

<a name="questionnaire"></a>
 ## questionnaire

| | |
|----|----|
|Element Id|QuestionnaireResponse.questionnaire|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[canonical](https://www.hl7.org/fhir/datatypes.html#canonical)([UKCoreQuestionnaire](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire))|

<br/>

 #### Definition

 The Questionnaire that defines and organizes the questions for which answers are being provided.

```json
"questionnaire": "https://fhir.nhs.uk/Questionnaire/COVIDVaccinationMedicalExemption",
```

 #### Requirements

 Needed to allow editing of the questionnaire response in a manner that enforces the constraints of the original form.

 #### Comment

 If a QuestionnaireResponse references a Questionnaire, then the QuestionnaireResponse structure must be consistent with the Questionnaire (i.e. questions must be organized into the same groups, nested questions must still be nested, etc.).

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|QuestionnaireResponse.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[QuestionnaireResponseStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/questionnaire-answers-status&#124;4.0.1) (Required) <br/>Lifecycle status of the questionnaire response. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 The position of the questionnaire response within its overall lifecycle.

 #### Requirements

 The information on Questionnaire resources  may possibly be gathered during multiple sessions and altered after considered being finished.

 #### Comment

 This element is labeled as a modifier because the status contains codes that mark the resource as not currently valid.

<a name="subject"></a>
 ## subject

| | |
|----|----|
|Element Id|QuestionnaireResponse.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient))|

<br/>

 #### Definition

 The subject of the questionnaire response.  This could be a patient, organization, practitioner, device, etc.  This is who/what the answers apply to, but is not necessarily the source of information.

```json
"subject": {
        "identifier": [
            {
                "system": "https://fhir.nhs.uk/Id/nhs-number",
                "value": "9912003888"
            }
        ],
        "display": "Ivor Fritagelse"
    },
```

 #### Requirements

 Allows linking the answers to the individual the answers describe.  May also affect access control.

 #### Comment

 If the Questionnaire declared a subjectType, the resource pointed to by this element must be an instance of one of the listed types.

 #### Constraints 

- **patient-reference** (*ERROR*) An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="subject.identifier.system"></a>
 ## subject.identifier.system

| | |
|----|----|
|Element Id|QuestionnaireResponse.subject.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="subject.identifier.value"></a>
 ## subject.identifier.value

| | |
|----|----|
|Element Id|QuestionnaireResponse.subject.identifier.value|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 The portion of the identifier typically relevant to the user and which is unique within the context of the system.

 #### Comment

 If the value is a full URI, then the system SHALL be urn:ietf:rfc:3986.  The value's primary purpose is computational mapping.  As a result, it may be normalized for comparison purposes (e.g. removing non-significant whitespace, dashes, etc.)  A value formatted for human display can be conveyed using the [Rendered Value extension](http://hl7.org/fhir/R4/extension-rendered-value.html). Identifier.value is to be treated as case sensitive unless knowledge of the Identifier.system allows the processer to be confident that non-case-sensitive processing is safe.

<a name="subject.display"></a>
 ## subject.display

| | |
|----|----|
|Element Id|QuestionnaireResponse.subject.display|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 Plain text narrative that identifies the resource in addition to the resource reference.

 #### Comment

 This is generally not the same as the Resource.text of the referenced resource.  The purpose is to identify what's being referenced, not to fully describe it.

<a name="authored"></a>
 ## authored

| | |
|----|----|
|Element Id|QuestionnaireResponse.authored|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 The date and/or time that this set of answers were last changed.

```json
"authored": "2021-09-09T08:32:00+00:00",
```

 #### Requirements

 Clinicians need to be able to check the date that the information in the questionnaire was collected, to derive the context of the answers.

 #### Comment

 May be different from the lastUpdateTime of the resource itself, because that reflects when the data was known to the server, not when the data was captured.  This element is optional to allow for systems that might not know the value, however it SHOULD be populated if possible.

<a name="author"></a>
 ## author

| | |
|----|----|
|Element Id|QuestionnaireResponse.author|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization) [NHSDigitalPractitionerRoleMinimal](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-Minimal))<br/> Aggregation - [contained](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 Person who received the answers to the questions in the QuestionnaireResponse and recorded them in the system.

```json
"author": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "B81001"
        },
        "display": "Austhorpe Springs Practice"
    },
```

 #### Requirements

 Need to know who interpreted the subject's answers to the questions in the questionnaire, and selected the appropriate options for answers.

 #### Comment

 Mapping a subject's answers to multiple choice options and determining what to put in the textual answer is a matter of interpretation.  Authoring by device would indicate that some portion of the questionnaire had been auto-populated.

<a name="author.identifier.system"></a>
 ## author.identifier.system

| | |
|----|----|
|Element Id|QuestionnaireResponse.author.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="author.identifier.value"></a>
 ## author.identifier.value

| | |
|----|----|
|Element Id|QuestionnaireResponse.author.identifier.value|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 The portion of the identifier typically relevant to the user and which is unique within the context of the system.

 #### Comment

 If the value is a full URI, then the system SHALL be urn:ietf:rfc:3986.  The value's primary purpose is computational mapping.  As a result, it may be normalized for comparison purposes (e.g. removing non-significant whitespace, dashes, etc.)  A value formatted for human display can be conveyed using the [Rendered Value extension](http://hl7.org/fhir/R4/extension-rendered-value.html). Identifier.value is to be treated as case sensitive unless knowledge of the Identifier.system allows the processer to be confident that non-case-sensitive processing is safe.

<a name="author.display"></a>
 ## author.display

| | |
|----|----|
|Element Id|QuestionnaireResponse.author.display|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 Plain text narrative that identifies the resource in addition to the resource reference.

 #### Comment

 This is generally not the same as the Resource.text of the referenced resource.  The purpose is to identify what's being referenced, not to fully describe it.

<a name="source"></a>
 ## source

| | |
|----|----|
|Element Id|QuestionnaireResponse.source|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole))<br/> Aggregation - [contained](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 The person who answered the questions about the subject.

 #### Requirements

 When answering questions about a subject that is minor, incapable of answering or an animal, another human source may answer the questions.

 #### Comment

 If not specified, no inference can be made about who provided the data.

 #### Constraints 

- **usercode-reference** (*WARNING*) An identifier reference or resource reference must be provided
- **usercode-nmc** (*ERROR*) NMC must be of the format NNANNNNA
- **usercode-gmp** (*ERROR*) GMP must be of the format GNNNNNNN and not be a spurious code (starts with G6 or G7)
- **usercode-gmc** (*ERROR*) GMC must be of the format CNNNNNNN
- **usercode-gphc** (*ERROR*) GPHC must be of the format NNNNNNN
- **usercode-hcpc** (*ERROR*) HCPC must be of the format AANNNNNN
- **usercode-din** (*ERROR*) DIN format must be NNNNNN

<a name="source.identifier"></a>
 ## source.identifier

| | |
|----|----|
|Element Id|QuestionnaireResponse.source.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier for the target resource. This is used when there is no way to reference the other resource directly, either because the entity it represents is not available through a FHIR server, or because there is no way for the author of the resource to convert a known identifier to an actual location. There is no requirement that a Reference.identifier point to something that is actually exposed as a FHIR instance, but it SHALL point to a business concept that would be expected to be exposed as a FHIR instance, and that instance would need to be of a FHIR resource type allowed by the reference.

 #### Comment

 When an identifier is provided in place of a reference, any system processing the reference will only be able to resolve the identifier to a reference if it understands the business context in which the identifier is used. Sometimes this is global (e.g. a national identifier) but often it is not. For this reason, none of the useful mechanisms described for working with references (e.g. chaining, includes) are possible, nor should servers be expected to be able resolve the reference. Servers may accept an identifier based reference untouched, resolve it, and/or reject it - see CapabilityStatement.rest.resource.referencePolicy.   When both an identifier and a literal reference are provided, the literal reference is preferred. Applications processing the resource are allowed - but not required - to check that the identifier matches the literal reference  Applications converting a logical reference to a literal reference may choose to leave the logical reference present, or remove it.  Reference is intended to point to a structure that can potentially be expressed as a FHIR resource, though there is no need for it to exist as an actual FHIR resource instance - except in as much as an application wishes to actual find the target of the reference. The content referred to be the identifier must meet the logical constraints implied by any limitations on what resource types are permitted for the reference.  For example, it would not be legitimate to send the identifier for a drug prescription if the type were Reference(Observation|DiagnosticReport).  One of the use-cases for Reference.identifier is the situation where no FHIR representation exists (where the type is Reference (Any).

<a name="source.display"></a>
 ## source.display

| | |
|----|----|
|Element Id|QuestionnaireResponse.source.display|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 Plain text narrative that identifies the resource in addition to the resource reference.

 #### Comment

 This is generally not the same as the Resource.text of the referenced resource.  The purpose is to identify what's being referenced, not to fully describe it.

<a name="item"></a>
 ## item

| | |
|----|----|
|Element Id|QuestionnaireResponse.item|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 A group or question item from the original questionnaire for which answers are provided.

```json
 "item": [
        {
            "linkId": "exemptionStatus",
            "answer": [
                {
                    "valueCoding": {
                        "system": "https://fhir.nhs.uk/CodeSystem/covid-vaccination-medical-exemption",
                        "code": "4",
                        "display": "Rejected: Exemption from COVID vaccination and testing"
                    }
                }
            ]
        }
   ]
```

 #### Comment

 Groups cannot have answers and therefore must nest directly within item. When dealing with questions, nesting must occur within each answer because some questions may have multiple answers (and the nesting occurs for each answer).

 #### Constraints 

- **qrs-1** (*ERROR*) Nested item can't be beneath both item and answer