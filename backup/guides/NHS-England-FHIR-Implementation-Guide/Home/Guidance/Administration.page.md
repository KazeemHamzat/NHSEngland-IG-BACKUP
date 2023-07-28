## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert">
  <i class="fas fa-exclamation-circle"></i><b> Important:</b> This page is under development by NHS Digital</div>

### Introduction

The administration module is covers core base data used within NHS (England) interoperability and data standards. The data model standards are document in the NHS Data Dictionary

NHS Digital provides a wide area of API and registries to support administration across the NHS (England)

These standards are supported in all NHS (England) versions of HL7 and these mirror real NHS concepts.  

<br/>

### Patient Registers

Track people involved in receiving healthcare, the basics nearly everything else references back to

<table class="regular assets">
<thead>
<tr>
<th>Name</th>
<th>NHS (England) or UK Profile</th>
<th>API or Registry</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Patient  {{link:http://hl7.org/fhir/StructureDefinition/Patient}}</td>
<td>{{pagelink:NHSDigital-Patient}}</td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir">Personal Demographics Service - FHIR API</a></td>
<td>Demographics and other administrative information about an individual or animal receiving care or other health-related services.</td>
</tr>
<tr>
<td>RelatedPersson {{link:http://hl7.org/fhir/StructureDefinition/RelatedPerson}}</td>
<td><a href="link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson">UKCore-RelatedPerson</a></td>
<td>See Personal Demographics Service - FHIR API</td>
<td>Information about a person that is involved in the care for a patient, but who is not the target of healthcare, nor has a formal responsibility in the care process.</td>
</tr>
<tr>
<td>Person {{link:http://hl7.org/fhir/StructureDefinition/Person}}</td>
<td></td>
<td></td>
<td>Demographics and administrative information about a person independent of a specific health-related context.</td>
</tr>
<tr>
<td>Group {{link:http://hl7.org/fhir/StructureDefinition/Group}}</td>
<td></td>
<td></td>
<td>Represents a defined collection of entities that may be discussed or acted upon collectively but which are not expected to act collectively, and are not formally or legally recognized; i.e. a collection of entities that isn't an Organization.</td>
</tr>
</tbody>
</table>


{{render:Diagams-administration-module-person}}

#### Related Standards 

<table class="regular assets">
<thead>
<tr>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Patient Notification Events</td>
<td>For PAS or MPI events see ADT_A28, ADT_A31 and ADT_A40 in <a href="https://github.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/blob/master/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf">HSCIC ITK HL7 V2 Message Specifications</a> <br> <br> For PDS see <a href="https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-notifications-fhir">Personal Demographics Service Notifications - FHIR</a></td>
</tr>
</tbody>
</table>

<br/>

#### Service Provider Directory Resources

Service Provider Directory resources are usually stored in the administration section of applications, and may even be synchronized from external systems.

<table class="regular assets">
<thead>
<tr>
<th>Name</th>
<th>NHS (England) or UK Profile</th>
<th>API or Registry</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Organization {{link:http://hl7.org/fhir/StructureDefinition/Organization}}</td>
<td>{{pagelink:NHSDigital-Organization}}</td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/organisation-data-service-fhir">Organisation Data Service - FHIR API</a> <br> <br> <a href="https://digital.nhs.uk/developer/api-catalogue/organisation-data-service-ord">Organisation Data Service - ORD API</a> <br> <br> <a href="https://digital.nhs.uk/services/organisation-data-service#access-our-data">Organisation Data Service</a></td>
<td>A formally or informally recognized grouping of people or organizations formed for the purpose of achieving some form of collective action. Includes companies, institutions, corporations, departments, community groups, healthcare practice groups, payer/insurer, etc.</td>
</tr>
<tr>
<td>Location {{link:http://hl7.org/fhir/StructureDefinition/Location}}</td>
<td>{{pagelink:NHSDigital-Location-duplicate-2}}</td>
<td>Details and position information for a physical place where services are provided and resources and participants may be stored, found, contained, or accommodated.</td>
<td></td>
</tr>
<tr>
<td>Practitioner {{link:http://hl7.org/fhir/StructureDefinition/Practitioner}}</td>
<td>{{pagelink:NHSDigital-Practitioner}} </td>
<td><a href="https://digital.nhs.uk/services/organisation-data-service#access-our-data">Organisation Data Service</a></td>
<td>A person who is directly or indirectly involved in the provisioning of healthcare.</td>
</tr>
<tr>
<td>PractitionerRole {{link:http://hl7.org/fhir/StructureDefinition/PractitionerRole}}</td>
<td> {{pagelink:NHSDigital-PractitionerRole}}</td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/spine-directory-service-ldap">Spine Directory Service - LDAP API</a></td>
<td>A specific set of Roles/Locations/specialties/services that a practitioner may perform at an organization for a period of time.</td>
</tr>
<tr>
<td>HealthcareService {{link:http://hl7.org/fhir/StructureDefinition/HealthcareService}}</td>
<td>{{pagelink:NHSDigital-HealthcareService}}</td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/directory-of-services-urgent-and-emergency-care-rest">Directory of Services - Urgent and Emergency Care - REST API</a> <br> <br> <a href="https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-directory-of-services">Electronic Prescription Service Directory of Services API</a></td>
<td>The details of a healthcare service available at a location.</td>
</tr>
<tr>
<td>Endpoint {{link:http://hl7.org/fhir/StructureDefinition/Endpoint}}</td>
<td>{{pagelink:SDS-Endpoint}}</td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/spine-directory-service-ldap">Spine Directory Service - LDAP API</a> <br> <br> <a href="https://digital.nhs.uk/developer/api-catalogue/spine-directory-service-fhir">Spine Directory Service - FHIR API</a></td>
<td>The technical details of an endpoint that can be used for electronic services, such as for web services providing XDS.b or a REST endpoint for another FHIR server. This may include any security context information.</td>
</tr>
</tbody>
</table>

{{render:Diagams-administration-module-prov-dir}}

<br/>

### Scheduling and Appointments 

The Scheduling/Appointment resources permit the planning of encounters to occur and follow on with other clinical activities.

<table class="regular assets">
<thead>
<tr>
<th>Name</th>
<th>NHS (England) or UK Profile</th>
<th>API or Registry	Description</th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<td>Schedule {{link:http://hl7.org/fhir/StructureDefinition/Schedule}}</td>
<td><a href="link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Schedule">UKCoreSchedule</a></td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir">Booking and Referral - FHIR API</a></td>
<td>A container for slots of time that may be available for booking appointments.</td>
</tr>
<tr>
<td>Slot {{link:http://hl7.org/fhir/StructureDefinition/Slot}}</td>
<td><a href="link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot">UKCore-Slot</a></td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir">Booking and Referral - FHIR API</a></td>
<td>A slot of time on a schedule that may be available for booking appointments.</td>
</tr>
<tr>
<td>Appointment {{link:http://hl7.org/fhir/StructureDefinition/Appointment}}</td>
<td><a href="link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment">UKCore-Appointment</a></td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir">Booking and Referral - FHIR API</a></td>
<td>A booking of a healthcare event among patient(s), practitioner(s), related person(s) and/or device(s) for a specific date/time. This may result in one or more Encounter(s).</td>
</tr>
<tr>
<td>AppointmentResponse {{link:http://hl7.org/fhir/StructureDefinition/AppointmentResponse}}</td>
<td></td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir">Booking and Referral - FHIR API</a></td>
<td>A reply to an appointment request for a patient and/or practitioner(s), such as a confirmation or rejection.</td>
</tr>
</tbody>
</table>

{{render:Diagams-administration-module-scheduling}}

#### Related Standards

<table class="regular assets">
<thead>
<tr>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Appointment Notification Events</td>
<td>For PAS events see ADT_A05 in <a href="https://github.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/blob/master/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf">HSCIC ITK HL7 V2 Message Specifications</a></td>
</tr>
</tbody>
</table>

<br/>

### Clinical Categorisation Resources 

Most clinical activities occur grouped in some way. Long term care is typically covered by an EpisodeOfCare, whereas short term care is covered by encounters. Account associates the tracking of transactions back to a Patient (or other resource). Flag is just used to highlight a warning or other notification about a patient (or other resource)

<table class="regular assets">
<thead>
<tr>
<th>Name</th>
<th>NHS (England) or UK Profile</th>
<th>Alias</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>EpisodeOfCare {{link:http://hl7.org/fhir/StructureDefinition/EpisodeOfCare}}</td>
<td><a href="https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare">EpisodeOfCare</a></td>
<td>Case Program</td>
<td>Problem	An association between a patient and an organisation / healthcare provider(s) during which time encounters may occur. The managing organisation assumes a level of responsibility for the patient during this time.</td>
</tr>
<tr>
<td>Encounter {{link:http://hl7.org/fhir/StructureDefinition/Encounter}}</td>
<td><a href="link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter">UKCore-Encounter</a></td>
<td>Visit</td>
<td>An interaction between a patient and healthcare provider(s) for the purpose of providing healthcare service(s) or assessing the health status of a patient.</td>
</tr>
<tr>
<td>Account {{link:http://hl7.org/fhir/StructureDefinition/Account}}</td>
<td></td>
<td>Cost centre</td>
<td>A financial tool for tracking value accrued for a particular purpose. In the healthcare field, used to track charges for a patient, cost centers, etc.</td>
</tr>
<tr>
<td>Flag {{link:http://hl7.org/fhir/StructureDefinition/Flag}}</td>
<td><a href="link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Flag">UKCore-Flag</a></td>
<td>Barriers to Care, Alert</td>
<td>Prospective warnings of potential issues when providing care to the patient.</td>
</tr>
</tbody>
</table>

{{render:Diagams-administration-module-interactions}}

#### Related Standards

<table class="regular assets">
<thead>
<tr>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Encounter Notification Events</td>
<td>For PAS events see ADT_A01, ADT_A02, ADT_A03, ADT_A04, etc in <a href="https://github.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/blob/master/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf">HSCIC ITK HL7 V2 Message Specifications</a></td>
</tr>
</tbody>
</table>