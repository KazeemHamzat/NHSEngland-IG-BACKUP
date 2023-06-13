### {{page-title}}


| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task) |  | trial-use | 

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
          <br><br>
          {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task, snapsho}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
         {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task, diff}}
        </div>
        <div id="Constraints"  class="tab-pane">
<br/>
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task'
for differential.element.constraint
select key, human, severity, expression
```

</div>
<div id="Examples"  class="tab-pane">
<br/>

- {{pagelink:Task-FormComplete}}
- {{pagelink:Task-FulfilPatientReferral}}
- {{pagelink:Task---Validate-Referral}}
- {{pagelink:Task---Review-LabReport}}
- {{pagelink:Task---Check-Prescription}}

</div>
</div>

<br/>


### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
```

#### Definition

 FHIR Task usage and scope is defined as 

> A task resource describes an activity that can be performed and tracks the state of completion of that activity. It is a representation that an activity should be or has been initiated, and eventually, represents the successful or unsuccessful completion of that activity. Note that there are a variety of processes associated with making and processing orders. Some orders may be handled immediately by automated systems but most require real world actions by one or more humans. Some orders can only be processed when other real world actions happen, such as a patient presenting themselves so that the action to be performed can actually be performed. Often these real world dependencies are only implicit in the order details.

**A Task resource often exists in parallel with clinical resources.** 

For example, a Task could request fulfillment of a ServiceRequest ordering a Procedure that would result in a Procedure, Observation, DiagnosticReport, ImagingStudy or similar resource. Another example would be a Task that requests fulfillment of a CommunicationRequest to be performed between various actors.

 #### Comment

 Task has three main uses: 

- basic delivery of an order resource (e.g. MedicationRequest or ServiceRequest)
- minor workflow requests (e.g. phone patient, complete form or validate a referral)
- workflow support (centred around complex workflow support and may involves a workflow engine)

##### Order Fulfilment

Centres on the fulfilment of the order. It does not contain the order details which are held in a referenced request resource. 
In the diagram below the recipient or fulfiller of the order uses FHIR Task to accept or reject the order, it also uses Task to send `event` updates. 
Note the fulfiller will use other resources to record the details of the fulfilment such as MedicationDispense for a MedicationRequest.

<img src="https://raw.githubusercontent.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/master/Diagams/Task-Deliver.PNG" width="60%"/>

Examples:

| Task.code | Task.status | Task.focus | Task.requester | Meaning | 
|--|--|--|--|
| fulfill | rejected | MedicationRequest | dispenser | The dispenser is rejecting the fulfilment/deliver of a referenced MedicationRequest. The MedicationRequest is not cancelled |
| fullfill | cancelled | MedicationRequest | any | The requested fulfilment of the MedicationRequest is cancelled. The referenced MedicationRequest is not cancelled |
| fullfill | accepted | MedicationRequest | dispenser | The dispenser is taking responsibility of fulfilling the referenced MedicationRequest. |
| fullfill | completed | MedicationRequest | dispenser | The requested fulfilment of the MedicationRequest is completed. The referenced MedicationRequest can now be changed to completed. |

See the section on `status` for more details.

<br/>

##### Minor Workflow Requests

This is used to implement additional around an order or to record specific workflow requests. These may not have a focused resource reference. It is anticipated they are coded using SNOMED CT.

<img src="https://raw.githubusercontent.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/master/Diagams/Task-Action.PNG" width="60%"/>
Examples:

| Task.code | Task.focus | Task.requester | Task.owner | Task.reasonCode | Meaning |
|--|--|--|--|--|
| 413292001 Assessment for referral | ServiceRequest | referrer |  clinician | 3457005 Patient Referral | Check the referenced referral is valid. |  
| 182836005 Review of medication |  | clinician | GP | 151715009 Emergency admission, asthma  | Request to review medication following an emergency admission. |  
| 103742009 Renewal of prescription | MedicationRequest | patient | GP |   | Request for a reissue/refill of a medication |  
| 324861000000109 Review of patient laboratory test report | DiagnosticReport | consultant | |   | Request for a lab report to be reviewed. See also <a href="https://nhsconnect.github.io/CareConnectAPI/engage_poc_uhscc.html">UHS Lab Reports</a> | 

The Task.status can be used to indicate fulfilment/delivery status.



<br/>

##### Workflow Support

More advanced workflow is supported, this adds in the use of Task.input and Task.output. This allows the passage of inputs and outputs which may be found in automated workflow activities.

The diagram below is from an acute trusts handling of a received eRS referral request. Each process communicates via the FHIR Task, the first process takes the eRS referral and gets the referral letter from eRS, these are then passed to the clinician for triage. Once triaged, the clinician creates a book appointment Task which the admin's action.

<img src="https://raw.githubusercontent.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/master/Diagams/Task-automated.PNG" width="60%"/>

 #### Constraints 

- **inv-1** (*ERROR*) Last modified date must be greater than or equal to authored-on date.


- <a href="#extension:agent">extension:agent</a>
- <a href="#extension:prescription">extension:prescription</a>
- <a href="#extension:repeatInformation">extension:repeatInformation</a>
- <a href="#identifier">identifier</a>
- <a href="#groupIdentifier">groupIdentifier</a>
- <a href="#status">status</a>
- <a href="#intent">intent</a>
- <a href="#code">code</a>
- <a href="#focus">focus</a>
- <a href="#for">for</a>
- <a href="#for.identifier.system">for.identifier.system</a>
- <a href="#authoredOn">authoredOn</a>
- <a href="#requester">requester</a>
- <a href="#owner">owner</a>
- <a href="#reasonCode">reasonCode</a>
- <a href="#reasonCode.coding:SNOMED">reasonCode.coding:SNOMED</a>
- <a href="#reasonCode.coding:SNOMED.system">reasonCode.coding:SNOMED.system</a>
- <a href="#note">note</a>
- <a href="#restriction">restriction</a>
- <a href="#restriction.period.end">restriction.period.end</a>
- <a href="#input">input</a>

<a name="extension:agent"></a>
 ## extension:agent

| | |
|----|----|
|Element Id|Task.extension:agent|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|agent|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionProvenanceAgent](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-Provenance-agent))|

<br/>

 #### Definition

 Is used as the author on request resources.

<a name="extension:prescription"></a>
 ## extension:prescription

| | |
|----|----|
|Element Id|Task.extension:prescription|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescription|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionEPSPrescription](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-Prescription))|

<br/>

 #### Definition

 ```json
"extension":  [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-Prescription",
            "extension":  [
                {
                    "url": "courseOfTherapyType",
                    "valueCoding": {
                        "system": "http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy",
                        "code": "acute",
                        "display": "Acute"
                    }
                }
            ]
        }
    ],
```

<a name="extension:repeatInformation"></a>
 ## extension:repeatInformation

| | |
|----|----|
|Element Id|Task.extension:repeatInformation|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|repeatInformation|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionEPSRepeatInformation](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation))|

<br/>

 #### Definition

 ```json
"extension": [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation",
            "extension": [
                {
                    "url": "numberOfRepeatsAllowed",
                    "valueUnsignedInt": 6
                },
                {
                    "url": "numberOfRepeatsIssued",
                    "valueUnsignedInt": 2
                }
            ]
        },
```

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Task.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 For **EPS**

A single identifier **MUST** be present and the value must be a UUID.

```json
"identifier":  [
        {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "5AC84C11-DB8B-44DA-8FCF-8980B3D13596"
        }
    ],
```

<a name="groupIdentifier"></a>
 ## groupIdentifier

| | |
|----|----|
|Element Id|Task.groupIdentifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 **EPS Only**

An identifier to the original `prescription-order` **MUST** be present. Only the short form identifier needs to be supplied.

```json
"groupIdentifier": {
        "system": "https://fhir.nhs.uk/Id/prescription-order-number",
        "value": "88AF6C-C81007-00001C"
    },
```

 #### Requirements

 Billing and/or reporting can be linked to whether multiple requests were created as a single unit.

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|Task.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[TaskStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/task-status&#124;4.0.1) (Required) <br/>The current status of the task. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 These workflow tasks have `status` which indicates the Task status. 

The following diagram reflects the "typical" state machine for Task. Note that not all states will be supported by all workflows and that some workflows may support additional transitions, including transitions from terminal states (e.g. back to "in-progress" from "failed" or "completed").

<img src="https://www.hl7.org/fhir/task-state-machine.svg"></img>

For example: 

A patient requesting a repeat prescription would ask for task with code `fulfil` used with `103742009 | Renewal of prescription` and a status of `requested`.  
Once reviewed (by a clinician), the task status would be changed to `accepted`. When the task is then picked up (`in-progress`) and the related *MedicationRequest* is sent, the status would change to `completed`.

 #### Requirements

 These states enable coordination of task status with off-the-shelf workflow solutions that support automation of tasks.

 #### Comment

 For **EPS**

Only `in-progress` is currently supported for reasonCode = 373784005 (Dispensing medication) and focus is a `dispense-notification`. 

`rejected` / `cancelled` / `failed` are supported for reasonCode = 33633005 (Prescription of drug) and focus is a `prescription-order`.

<a name="intent"></a>
 ## intent

| | |
|----|----|
|Element Id|Task.intent|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[TaskIntent](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/task-intent&#124;4.0.1) (Required) <br/>Distinguishes whether the task is a proposal, plan or full order. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 Indicates the "level" of actionability associated with the Task, i.e. i+R[9]Cs this a proposed task, a planned task, an actionable task, etc.

 #### Comment

 Is not processed by EPS and is included for FHIR compliance reasons. The value should always be `order`.

<a name="code"></a>
 ## code

| | |
|----|----|
|Element Id|Task.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDigitalTaskCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-task-code) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 **e-RS** 

A SNOMED CT procedure code to indicate the action

```json
  "code": {
        "coding": [
            {
                "system": "http://snomed.info/sct",
                "code": "386053000",
                "display": "Evaluation procedure"
            }
        ]
    },
```

**EPS**

The SNOMED action codes are complemented with `order delivery` [task-code](https://www.hl7.org/fhir/valueset-task-code.html) which indicates the type of action to be performed against the focal resource. 

For example:

The code `fulfil` used with `182836005 | Review of medication` means a task to review medication.
The code `approve` used with `103742009 | Renewal of prescription` is a task for a clinician to approve the issue of a repeat medication.

```json
 "code": {
        "coding":  [
            {
                "system": "http://hl7.org/fhir/CodeSystem/task-code",
                "code": "fulfill",
                "display": "Fulfill the focal request"
            }
        ]
 ```

 #### Comment

 The title (eg "My Tasks", "Outstanding Tasks for Patient X") should go into the code.

<a name="focus"></a>
 ## focus

| | |
|----|----|
|Element Id|Task.focus|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalAppointment](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Appointment) [NHSDigitalServiceRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-ServiceRequest) [NHSDigitalBundleFHIRMessage](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Bundle-FHIRMessage) [NHSDigitalMedicationRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest) [UKCorePatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient))|

<br/>

 #### Definition

 **e-RS**

Reference to the resource which is the focus of the action 

```json
 "focus": {
        "reference": "https://server.fire.ly/ServiceRequest/eb13327f-e990-4667-b37a-89eb93a94c47"
    },
```

** EPS Only**

This will be the `Bundle.identifier` of the message this Task is acting on. 
For Tasks with a reasonCode of `373784005 - Dispensing medication`  this will be a `dispense-notification` message. 
For Tasks with a reasonCode of `33633005 - Prescription of drug` this will be the `prescription-order` message from the Task/$release operation.

```json
"focus": {
        "type": "Bundle",
        "identifier": {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "334a3195-1f6c-497a-8efe-d272ca9c4e38"
        }
    },
```

 #### Requirements

 Used to identify the thing to be done.

 #### Comment

 Tasks are often generated as a consequence of other workflows or relate to FHIR Workflow resources. For example a repeat medication request will be related to a previous `MedicationRequest` or a medication reconciliation may relate to a hospital admissions `Encounter/EpisodeOfCare`. This is carried in the `focus` element.

`focus` can be omitted. For example if an ED generated a Medication Review as a result of COPD Emergency encounter they may chose to include a reference to the Encounter but they may decide instead to use a more specific reasonCode such as `394720003 | Asthma medication review`.

 #### Constraints 

- **nhsd-taskfocus** (*ERROR*) focus - An identifier reference or resource reference must be provided

<a name="for"></a>
 ## for

| | |
|----|----|
|Element Id|Task.for|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Resource](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Resource))|

<br/>

 #### Definition

 A reference to the patient the Task is for. This will always be an identifier reference using the Patients NHSNumber.

```json
"for": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9446368138"
        }
    },
```

 #### Requirements

 Used to track tasks outstanding for a beneficiary.  Do not use to track the task owner or creator (see owner and creator respectively).  This can also affect access control.

 #### Constraints 

- **patient-reference** (*ERROR*) An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) NHS Number must be in the English and Welsh NHS Number range or length of the number is wrong.

<a name="for.identifier.system"></a>
 ## for.identifier.system

| | |
|----|----|
|Element Id|Task.for.identifier.system|
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
|Element Id|Task.authoredOn|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 Date and time the task was created.

```json
"authoredOn": "2020-12-21T17:03:20-00:00",
```

 #### Requirements

 Most often used along with lastUpdated to track duration of task to supporting monitoring and management.

<a name="requester"></a>
 ## requester

| | |
|----|----|
|Element Id|Task.requester|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole))<br/> Aggregation - [contained](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

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
    "resourceType": "Task",
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
            "telecom": [
                {
                    "system": "phone",
                    "use": "work",
                    "value": "01234567890"
                }
            ]
        }
    ],
```

 #### Requirements

 Identifies who created this task.  May be used by access control mechanisms (e.g., to ensure that only the creator can cancel a task).

<a name="owner"></a>
 ## owner

| | |
|----|----|
|Element Id|Task.owner|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole) [NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization))|

<br/>

 #### Definition

 **EPS**

Who is responsible for actioning the request Task (e.g. for a prescription-order this will be the pharmacy). 

```json
"owner": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "FB444"
        },
        "display": "Freds Pharmacy"
    },
```

**e-RS**

```json
"owner": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ers-service",
            "value": "12444"
        }
    },
```

 #### Requirements

 Identifies who is expected to perform this task.

 #### Comment

 Tasks may be created with an owner not yet identified.

<a name="reasonCode"></a>
 ## reasonCode

| | |
|----|----|
|Element Id|Task.reasonCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 In FHIR Task these types of workflow would be represented via **reasonCode** and/or **reasonReference**

For medication this is probably SNOMED CT based using codes under the SNOMED CT 182832007 Medication management and includes codes such as:

| SNOMED CT | Display |
|--|--|
| 33633005 | Prescription of drug |
| 373784005 | Dispensing medication |

<br/>

For referral management

| SNOMED CT | Display |
|--|--|
| <a href="https://ontoserver.csiro.au/shrimp/?concept=3457005&version=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%2Fversion%2F20211124&valueset=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%3Ffhir_vs&fhir=https%3A%2F%2Fontology.nhs.uk%2Fauthoring%2Ffhir">3457005</a> | Patient Referral |
| <a href="https://ontoserver.csiro.au/shrimp/?concept=185499000&version=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%2Fversion%2F20211124&valueset=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%3Ffhir_vs&fhir=https%3A%2F%2Fontology.nhs.uk%2Fauthoring%2Ffhir">185499000</a>| Expedite appointment |

 #### Comment

 This should only be included if there is no focus or if it differs from the reason indicated on the focus.

<a name="reasonCode.coding:SNOMED"></a>
 ## reasonCode.coding:SNOMED

| | |
|----|----|
|Element Id|Task.reasonCode.coding:SNOMED|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|SNOMED|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="reasonCode.coding:SNOMED.system"></a>
 ## reasonCode.coding:SNOMED.system

| | |
|----|----|
|Element Id|Task.reasonCode.coding:SNOMED.system|
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

<a name="note"></a>
 ## note

| | |
|----|----|
|Element Id|Task.note|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Annotation](https://www.hl7.org/fhir/datatypes.html#Annotation)|

<br/>

 #### Definition

 **EPS Only**

This may contain cancellation reason.

**e-RS**

Used to add notes to the worklist items

```json
"note": [
    {
      "text": "Optional comments"
    }
  ]
```

<a name="restriction"></a>
 ## restriction

| | |
|----|----|
|Element Id|Task.restriction|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 If the Task.focus is a request resource and the task is seeking fulfillment (i.e. is asking for the request to be actioned), this element identifies any limitations on what parts of the referenced request should be actioned.

 #### Requirements

 Sometimes when fulfillment is sought, you don't want full fulfillment.

<a name="restriction.period.end"></a>
 ## restriction.period.end

| | |
|----|----|
|Element Id|Task.restriction.period.end|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 In **e-RS** this is also known as the review date due.

 #### Comment

 **e-RS**

- If deferred to provider (because there were no appointments available for a directly bookable service) then this is the date by which the provide should resolve the appointment slot issue; or
- If the referral was sent to a triage service then this is the date by which the provider should have reviewed the referral

<a name="input"></a>
 ## input

| | |
|----|----|
|Element Id|Task.input|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 Additional information that may be needed in the execution of the task.

 #### Requirements

 Resources and data used to perform the task.  This data is used in the business logic of task execution, and is stored separately because it varies between workflows.