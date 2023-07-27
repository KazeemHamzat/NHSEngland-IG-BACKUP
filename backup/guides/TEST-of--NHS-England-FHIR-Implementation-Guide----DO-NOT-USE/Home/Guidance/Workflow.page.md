## {{page-title}}
 
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS Digital</div>
   
 Workflow used within the NHS can be split into two general patterns. 

<br/>
<br/>

- FHIR Workflow via a Broker. Usage examples:
  - Electronic Referral Service (eRS)
  - Electronic Prescription Service (EPS)

<br/>

- Event Sharing. Usage examples:
  - Vaccinations Event Sharing

<br/>

- Ad-Hoc Workflow Communication Patterns. Usage examples:
  - Pathology
  - Booking and Referral Standard (BARS)

<br/>



<div class="nhsd-!t-margin-bottom-6">
  <ul class="nav nav-tabs" role="tablist">
    <li role="presentation"  class="active">
            <a href="#broker" role="tab" data-toggle="tab">FHIR Workflow Management with a Broker</a>
    </li>
     <li role="presentation">
            <a href="#sharing" role="tab" data-toggle="tab">Event Sharing Patterns</a>
    </li>
    <li role="presentation">
            <a href="#adhoc" role="tab" data-toggle="tab">Ad-Hoc Workflow Communication Patterns</a>
    </li>
  </ul>
  <div class="tab-content snippet"> 
<div id="broker" role="tabpanel" class="tab-pane active">

<br/>

Workflow Management with a broker includes a central registry which allows the coordination of the workflow activities. Within NHS Digital these generally follow [FHIR Workflow Management](https://hl7.org/fhir/workflow-management.html#optionh) with a Broker pattern.

{{render:Diagams-workflow-optionh}}

Examples within NHS Digital include: 

<br/>

#### Electronic Referral Service (eRS)

The following description is a high-level representation of eRS. Some of the interactions are not currently implemented.

{{render:Diagams-workflow-ers}}

1. The referral is sent by the referrer to eRS via the FHIR RESTful POST /ServiceRequest end point. Note: this may also include sending of referral supporting information, see eRS documentation for more details.
2. Internally eRS will create a fulfilment Task and work item Tasks as required.
3. The service (filler) of these Tasks is notified (need to check if this is true enough?).
4. The service may claim or action these Tasks
5. As the ServiceRequest is being actioned/fulfilled, the service will generate event notifications. These are generally out of scope for eRS workflow and will include a wide variety of event notifications such as ADT messages, discharge letters, etc.
6. The ServiceRequest or Task is marked as completed and this closes the referral or work flow item. 
7. The referrer and service can check on the status of the Task/ServiceRequest as required via querying eRS endpoints

<br/>

#### Electronic Prescription Service (EPS)

EPS does not support notifications and due to technical & legal constraints, the Request (2) and Events (5a and 6) interactions use FHIR Messaging.

{{render:Diagams-workflow-eps}}

1. The prescription-order is signed by sending the prescription-order FHIR Message via POST /$prepare endpoint (https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Prescribing-prepare-prescription)
2. The signature section is added to the prescription-order FHIR Message and this is sent to EPS via the POST /$process-message endpoint (https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Prescribing-send-prescription-order-message)
3. Internally within EPS this FHIR Message is converted to a HL7v3 ParentPrescription and the top level of this structure is represented as a FHIR Task (prescription).
4. The dispenser polls EPS for prescriptions to act upon or retrieves specific prescriptions via the FHIR Operation POST /Task/$release endpoint (https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Dispensing-release)
5. As the dispenser fulfils the prescription-order they will generate dispense-notifications and/or return/cancel the Task (prescription). Note this actions and those by the prescriber (6) have no set sequence.
6. The dispenser sends a series of FHIR Message dispense-notifications (and dispense-notification-updates) to EPS via the POST /$process-message endpoint. (https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Dispensing-return). These notifications update the Task (prescription) and the fulfilment Task is deemed as completed by statuses in the dispense-notification.
7. The dispenser returns the prescription (they can't fulfil the prescription-order) or cancels the fulfilment of the prescription order (the prescription-order has issues) via the FHIR RESTful POST /Task endpoint (https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Dispensing-return)
8. The prescriber can cancel the prescription-order via the FHIR Message POST /$process-message endpoint (https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Prescribing-send-prescription-order-update-message) 
9. The prescriber or dispenser can check the overall status of the prescription fulfilment via the FHR RESTful GET /Task endpoint (https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Tracker-get-task)


</div>
<div id="adhoc" class="tab-pane">

<br/>

These patterns are often implemented with middleware support, these can be a number of components such as a Trust Integration Engine (TIE), Message Queue (MQ)/MESH, etc. The communication is generally point to point between the placer and the filler. 

FHIR documentation on these patterns can be found on [Ad-Hoc Workflow Communication Patterns](http://hl7.org/fhir/R4/workflow-ad-hoc.html). In particular [Messaging request from placer to filler & acknowledgment](http://hl7.org/fhir/R4/workflow-ad-hoc.html#optiond)

<br/>

#### Pathology

Pathology is commonly implemented in the NHS using HL7 v2 Messages. The national standards follow a similar pattern using EDIFACT, HL7 v3 and FHIR STU3 Pathology Messages. The HL7 FHIR version is used for illustration of the pattern.

{{render:Diagams-workflow-pathology}}

1. The Test Request is created in the EPR or Order Comms software, it is sent to the laboratory via the TIE. (HL7 v2.4 OML_O21 - Laboratory order) 
2. The TIE forwards on the request to the Laboratory
3. The laboratory performs the test and send out the results via the TIE. (HL7 v2.4 ORU_R01 - Unsolicited transmission of an observation message)
4. The TIE forwards the results (response) to the requester, this response may also go via MESH is the requester is in primary care sector. The TIE may choose to distribute the results to other recipients.


#### Booking and Referral Standard

BARS is designed around traditional point to point messaging exchanges which are implemented as FHIR Messages. This is similar to Pathology workflow above with the addition of a central registry to record ServiceRequests. It is also similar to HL7 v2.4 REF_I12 Patient Referral and associated response messages (REF_I13 Modify Patient Referral and REF_I14 Cancel Patient Referral

{{render:Diagams-workflow-bars}}

1. The referral is sent to the BARS POST /$process-message endpoint (https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir#api-Message-processMessage)
2. This referral is then routed to the services POST /$process-message endpoint
3. The service can respond via the BARS POST /$process-message endpoint (https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir#api-Message-processMessage)
4. This response is then routed to the referrers POST /$process-message endpoint
5. As the ServiceRequest is being actioned/fulfilled, the service will generate event notifications. These are generally out of scope for eRS workflow and will include a wide variety of event notifications such as ADT messages, discharge letters, etc.
6. The referrer and service can check on the status of the referral as required via querying BARS FHIR RESTful ServiceRequest endpoint (https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir#api-Referral)

</div>
<div id="sharing" class="tab-pane">

<br/>

Event Sharing is sub section of FHIR Workflow Management which focuses on the events generated from a request. 

#### COVID19 Vaccinations

COVID19 is in part a traditional messaging middleware pattern called [Dynamic Router](https://www.enterpriseintegrationpatterns.com/patterns/messaging/DynamicRouter.html) which uses FHIR STU3 Messages and a FHIR R4 RESTful API. 
This broadly aligns to [Direct POST of request to fulfiller's system](https://www.hl7.org/fhir/workflow-ad-hoc.html#optionb), in particular interaction (3). The other interactions exist but are not technical interactions. 

{{render:COVIDworkflow}}

##### Overview 

1. COVID19 and Seasonal Flu Vaccinations are fed to a central database called DPS via the [Vaccinations APIs](https://digital.nhs.uk/developer/api-catalogue/vaccination). This is a CSV based implementation of the 
{{pagelink:NHSDigital-Immunization}} profile.

2. From DPS the vaccination events are distributed to providers, including:

- Patients GP via [Digital Medicine FHIR](https://digital.nhs.uk/developer/api-catalogue/digital-medicine-fhir)
- Other providers via a subscription to the NEMS events [Vaccination Events FHIR](https://digital.nhs.uk/developer/api-catalogue/vaccination-events-fhir)
- National Immunisation Service via a Vaccination Feed.

3a. The vaccinations held within DPS can be directly queried by [Immunisation History FHIR](https://digital.nhs.uk/developer/api-catalogue/immunisation-history-fhir). Citizens will use this API via NHS/certification Apps for COVID19 Immunisations.

3b. GP and Child Health may choose to use the local copy of the Immunization or use the FHIR RESTful API (3a)

The data model and FHIR profile for `Vaccination Feed` and `Immunization History FHIR` can be found here {{pagelink:NHSDigital-Immunization}}





</div
</div>
</div>

