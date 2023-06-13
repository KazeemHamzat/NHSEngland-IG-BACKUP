## NHSDigital-DocumentReference

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Experimental. This page is for illustration of a concept</div>

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-DocumentReference](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-DocumentReference) |  | draft |

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
          <br><br>
  with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DocumentReference}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-DocumentReference, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
   from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DocumentReference}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-DocumentReference, diff}}
        </div>
<div id="Examples"  class="tab-pane">
<br />

 - {{pagelink:MentalHealthCrisisPlan}}
</div>
</div>

---
<br/>

### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/NHSDigital-DocumentReference' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
```

---

 #### Definition

 A reference to a document of any kind for any purpose. Provides metadata about the document so that the document can be discovered and managed. The scope of a document is any seralised object with a mime-type, so includes formal patient centric documents (CDA), clinical notes, scanned paper, and non-patient specific documents like policy text.

 #### Comment

 Usually, this is used for documents other than those defined by FHIR.


- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#type">type</a>
- <a href="#category">category</a>
- <a href="#subject">subject</a>
- <a href="#date">date</a>
- <a href="#author">author</a>
- <a href="#custodian">custodian</a>
- <a href="#content">content</a>
- <a href="#content.attachment">content.attachment</a>
- <a href="#content.attachment.data">content.attachment.data</a>
- <a href="#content.attachment.url">content.attachment.url</a>
- <a href="#context">context</a>
- <a href="#context.practiceSetting">context.practiceSetting</a>
- <a href="#context.related">context.related</a>

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|DocumentReference.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 Other identifiers associated with the document, including version independent identifiers.

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|DocumentReference.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[DocumentReferenceStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/document-reference-status&#124;4.0.1) (Required) <br/>The status of the document reference. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 The status of this document reference.

 #### Comment

 This is the status of the DocumentReference object, which might be independent from the docStatus element.  This element is labelled as a modifier because the status contains the codes that mark the document or reference as not currently valid.

<a name="type"></a>
 ## type

| | |
|----|----|
|Element Id|DocumentReference.type|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDigitalDocumentType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-DocumentType) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Specifies the particular kind of document referenced  (e.g. History and Physical, Discharge Summary, Progress Note). This usually equates to the purpose of making the document referenced.

```json
"type": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "736253002",
                "display": "Mental health crisis plan"
            }
        ]
    }
```

 #### Comment

 Key metadata element describing the document that describes he exact type of document. Helps humans to assess whether the document is of interest when viewing a list of documents.

<a name="category"></a>
 ## category

| | |
|----|----|
|Element Id|DocumentReference.category|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[DocumentClassValueSet](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/document-classcodes) (Example) <br/>High-level kind of a clinical document at a macro level. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 A categorisation for the type of document referenced - helps for indexing and searching. This may be implied by or derived from the code specified in the DocumentReference.type.

```json
"category":  [
        {
            "coding":  [
                {
                    "system": "http://snomed.info/sct",
                    "code": "734163000",
                    "display": "Care plan"
                }
            ]
        }
    ]
```

 #### Comment

 Key metadata element describing the the category or classification of the document. This is a broader perspective that groups similar documents based on how they would be used. This is a primary key used in searching.

<a name="subject"></a>
 ## subject

| | |
|----|----|
|Element Id|DocumentReference.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Group](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Group) [Device](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Device) [UKCorePractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner) [NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient))|

<br/>

 #### Definition

 A reference to a [NHSDigital-Patient](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient) and/or an identifier reference using NHSNumber. Only traced NHS Numbers may be used. 

```json

    "subject": {
        "reference": "urn:uuid:edea022a-2d81-11eb-adc1-0242ac120002",
        "identifier": [
            {
                "system": "https://fhir.nhs.uk/Id/nhs-number",
                "value": "9912003888"
            }
        ]
    },

```

Preference is for a reference to a Patient resource, however current document flows may only support limited metadata.

 #### Constraints 

- **patient-reference** (*WARNING*) subject - An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="date"></a>
 ## date

| | |
|----|----|
|Element Id|DocumentReference.date|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[instant](https://www.hl7.org/fhir/datatypes.html#instant)|

<br/>

 #### Definition

 When the document reference was created.

 #### Comment

 Referencing/indexing time is used for tracking, organising versions and searching.

<a name="author"></a>
 ## author

| | |
|----|----|
|Element Id|DocumentReference.author|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization) [Device](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Device) [NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient) [UKCoreRelatedPerson](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson) [NHSDigitalPractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole))|

<br/>

 #### Definition

 A resource reference to a contained [NHSDigital-PractitionerRole](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole)

```json

    "author": [
        {
          "reference" : "#author",
        }
    ]
```

The contained resource: 

```json
{
  "resourceType": "DocumentReference",
  "id": "a9b9f0f4-cc37-4ea3-bd4b-16d15ddbe63b",
  "contained": [
    {
      "resourceType": "PractitionerRole",
      "id": "author",
      "practitioner": {
        "identifier": {
          "system": "https://fhir.nhs.uk/Id/sds-user-id",
          "value": "0987654321"
        }
      },
      "organization": {
        "identifier": {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "RR8"
        },
        "display": "LEEDS TEACHING HOSPITALS NHS TRUST"
      }
    }
  ],
```

 #### Comment

 Not necessarily who did the actual data entry (i.e. typist) or who was the source (informant).

<a name="custodian"></a>
 ## custodian

| | |
|----|----|
|Element Id|DocumentReference.custodian|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization))|

<br/>

 #### Definition

 An identifier reference to an ODS Organisation. 

```json

        "custodian": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "VNE51"
                },
                "display": "The Pharmacy System"
        }
```

 #### Comment

 Identifies the logical organization (software system, vendor, or department) to go to find the current version, where to report issues, etc. This is different from the physical location (URL, disk drive, or server) of the document, which is the technical location of the document, which host may be delegated to the management of some other organization.

<a name="content"></a>
 ## content

| | |
|----|----|
|Element Id|DocumentReference.content|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 The document and format referenced. There may be multiple content element repetitions, each with a different format.

```json
"content": [
        {
            "attachment": {
                "extension": [
                    {
                        "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-eRS-AttachedBy",
                        "valueReference": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/sds-user-id",
                                "value": "987654321"
                            }
                        }
                    }
                ],
                "contentType": "application/pdf",
                "url": "Binary/att-70001-70002",
                "size": 18592,
                "title": "upload.png",
                "creation": "2022-01-31"
            }
        }
    ]
```

<a name="content.attachment"></a>
 ## content.attachment

| | |
|----|----|
|Element Id|DocumentReference.content.attachment|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Attachment](https://www.hl7.org/fhir/datatypes.html#Attachment)|

<br/>

 #### Definition

 The document or URL of the document along with critical metadata to prove content has integrity.

<a name="content.attachment.data"></a>
 ## content.attachment.data

| | |
|----|----|
|Element Id|DocumentReference.content.attachment.data|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[base64Binary](https://www.hl7.org/fhir/datatypes.html#base64Binary)|

<br/>

 #### Definition

 **SHOULD** not be used. Use url to link to the actual document

 #### Requirements

 The data needs to able to be transmitted inline.

 #### Comment

 The base64-encoded data SHALL be expressed in the same character set as the base resource XML or JSON.

<a name="content.attachment.url"></a>
 ## content.attachment.url

| | |
|----|----|
|Element Id|DocumentReference.content.attachment.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[url](https://www.hl7.org/fhir/datatypes.html#url)|

<br/>

 #### Definition

 For REST interactions this **MUST** be a url to the actual document. For messaging interactions this must be an internal resource reference to the actual document.

 #### Requirements

 The data needs to be transmitted by reference.

 #### Comment

 If both data and url are provided, the url SHALL point to the same content as the data contains. Urls may be relative references or may reference transient locations such as a wrapping envelope using cid: though this has ramifications for using signatures. Relative URLs are interpreted relative to the service url, like a resource reference, rather than relative to the resource itself. If a URL is provided, it SHALL resolve to actual data.

<a name="context"></a>
 ## context

| | |
|----|----|
|Element Id|DocumentReference.context|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 The clinical context in which the document was prepared.

```json
"context": {
        "related" : [
            {
                "type": "ServiceRequest",
                "reference": "ServiceRequest/be735573-9f24-42e1-ae98-af89d632e4bf"
            },
            {
                "type": "Task",
                "reference": "Task/f66e4cd7-207c-4b7d-9ac9-80630c451125"
            }
        ]
    }
```

 #### Comment

 These values are primarily added to help with searching for interesting/relevant documents.

<a name="context.practiceSetting"></a>
 ## context.practiceSetting

| | |
|----|----|
|Element Id|DocumentReference.context.practiceSetting|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDigitalCareSettingType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-CareSettingType) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 It is recommended a care setting code should be provided

 #### Requirements

 This is an important piece of metadata that providers often rely upon to quickly sort and/or filter out to find specific content.

 #### Comment

 This element should be based on a coarse classification system for the class of specialty practice. Recommend the use of the classification system for Practice Setting, such as that described by the Subject Matter Domain in LOINC.

<a name="context.related"></a>
 ## context.related

| | |
|----|----|
|Element Id|DocumentReference.context.related|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalServiceRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-ServiceRequest) [NHSDigitalTask](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task))|

<br/>

 #### Definition

 Related identifiers or resources associated with the DocumentReference.

In eRS this is used to link a DocumentReference (i.e. a document) to a ServiceRequest and/or Task.

 #### Comment

 May be identifiers or resources that caused the DocumentReference or referenced Document to be created.