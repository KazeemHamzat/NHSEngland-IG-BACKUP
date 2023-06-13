## NHSDigital-CommunicationRequest


| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-CommunicationRequest}](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-CommunicationRequest) | | trial-use |

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
          {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-CommunicationRequest, hybrid}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
         {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-CommunicationRequest, diff}}
        </div>
<div id="Examples"  class="tab-pane">

  - {{pagelink:in-appmessage}}
  - {{pagelink:pushnotification}}
  - {{pagelink:EPSNotification}}
  - {{pagelink:EPSMedicationDispatch}}
  - {{pagelink:EPSPrescriptionCancel}}

</div>
</div>

---
<br>


<br/>

 #### Definition

 A request to convey information; e.g. the CDS system proposes that an alert be sent to a responsible provider, the CDS system proposes that the public health agency be notified about a reportable condition.


- <a href="#status">status</a>
- <a href="#subject">subject</a>
- <a href="#payload">payload</a>
- <a href="#requester">requester</a>
- <a href="#recipient">recipient</a>

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|CommunicationRequest.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[RequestStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/request-status&#124;4.0.1) (Required) <br/>The status of the communication request. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 The status of the proposal or order.

<a name="subject"></a>
 ## subject

| | |
|----|----|
|Element Id|CommunicationRequest.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient))|

<br/>

 #### Definition

 The patient or group that is the focus of this communication request.

```json
"subject": {
        "type": "Patient",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9453740519"
        }
    }
```

 #### Constraints 

- **patient-reference** (*WARNING*) subject - An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="payload"></a>
 ## payload

| | |
|----|----|
|Element Id|CommunicationRequest.payload|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 #### NHSApp

**In App Messages** 

NHSApp supports a subset of Markdown for in-app messages, please see API documentation for more details. Only `contentString` is supported.

```json
  
    "payload":  [
        {
            "contentString": "You have a new appointment, please confirm you can attend. Open the Onboarded Third Party appointment [here](https://www.nhsapp.service.nhs.uk/appointments/hospital-appointments)"
        }
    ]
```

**Push Notifications**

Only `contentReference` is supported and this should contain the URL to a page within the NHS App to be opened when the notification is tapped. If this property is not specified, the App will open on the home screen.

```json
  
    "payload":  [
        {
            "contentReference": {
                "reference": "https://www.nhsapp.service.nhs.uk/patient/messages/app-messaging",
                "display": "You have a new message. The message may contain something important."
            }
        }
    ],
```

#### EPS

**CommunicationRequest** is used in Electronic Prescription Service (EPS) to convey patient specific information. This includes:

* patient information - messages to the patient
* medications - list of authorised repeat medications which is contained on a FHIR List resource, details and example list of repeat medications can be found in profile `UKCore-List`

These would be traditionally printed on the right hand side of the FP10 stationery.

**CommunicationRequest should not contain Clinical information regarding the prescriptions, these should be conveyed in the MedicationRequest resource.**

```json

    "payload":  [
        {
            "contentString": "Please make an appointment to see your GP. Review date due"
        },
        {
            "contentReference": {
                "reference": "urn:uuid:d0f003a0-8763-43d5-a264-ce52a38901c9",
                "display": "List of Repeat Medications for re-ordering"
            }
        }
    ],
```

 #### Comment

 The payload will consist of message to the Patient and/or a reference to a list of active repeat medications.

<a name="requester"></a>
 ## requester

| | |
|----|----|
|Element Id|CommunicationRequest.requester|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient) [NHSDigitalPractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole) [NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization))|

<br/>

 #### Definition

 The person/organisation making the communication request. This **SHOULD** use reference identifiers.

```json

    "requester": {
        "type": "Organization",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RBA"
        },
        "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
    },
```

<a name="recipient"></a>
 ## recipient

| | |
|----|----|
|Element Id|CommunicationRequest.recipient|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Group](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Group) [CareTeam](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/CareTeam) [NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization) [NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient) [NHSDigitalPractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner) [NHSDigitalPractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole) [NHSDigitalHealthcareService](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-HealthcareService))|

<br/>

 #### Definition

 The persons/organisations who will receive the communication request. This **SHOULD** use reference identifiers.

```json

    "recipient":  [
        {
            "type": "Patient",
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/nhs-number",
                "value": "9453740519"
            }
        }
    ]
```