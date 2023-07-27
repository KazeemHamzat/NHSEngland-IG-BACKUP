## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS Digital</div>

### Introduction

The administration module is covers core base data used within NHS (England) interoperability and data standards. The data model standards are document in the NHS Data Dictionary

NHS Digital provides a wide area of API and registries to support administration across the NHS (England)

These standards are supported in all NHS (England) versions of HL7 and these mirror real NHS concepts.  

<br/>

### Patient Registers

Track people involved in receiving healthcare, the basics nearly everything else references back to


|Name | NHS (England) or UK Profile |	API or Registry	 |Description |
|--
| Patient {{link:http://hl7.org/fhir/StructureDefinition/Patient}} | {{pagelink:NHSDigital-Patient}} | [Personal Demographics Service - FHIR API](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir) | Demographics and other administrative information about an individual or animal receiving care or other health-related services. | 
| RelatedPersson {{link:http://hl7.org/fhir/StructureDefinition/RelatedPerson}}	| [UKCore-RelatedPerson](link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson) | See Personal Demographics Service - FHIR API | Information about a person that is involved in the care for a patient, but who is not the target of healthcare, nor has a formal responsibility in the care process. |
| Person {{link:http://hl7.org/fhir/StructureDefinition/Person}} | | | Demographics and administrative information about a person independent of a specific health-related context. |
| Group {{link:http://hl7.org/fhir/StructureDefinition/Group}}	| | | 	Represents a defined collection of entities that may be discussed or acted upon collectively but which are not expected to act collectively, and are not formally or legally recognized; i.e. a collection of entities that isn't an Organization. |


{{render:Diagams-administration-module-person}}

#### Related Standards 


| Type | Description |
|--
|  Patient Notification Events | For PAS or MPI events see ADT_A28, ADT_A31 and ADT_A40 in [HSCIC ITK HL7 V2 Message Specifications](https://github.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/blob/master/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf) <br/> <br/> For PDS see [Personal Demographics Service Notifications - FHIR](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-notifications-fhir) |

<br/>

#### Service Provider Directory Resources

Service Provider Directory resources are usually stored in the administration section of applications, and may even be synchronized from external systems.

| Name | NHS (England) or UK Profile | API or Registry	| Description |
|--
| Organization {{link:http://hl7.org/fhir/StructureDefinition/Organization}} | {{pagelink:NHSDigital-Organization}}  | [Organisation Data Service - FHIR API](https://digital.nhs.uk/developer/api-catalogue/organisation-data-service-fhir) <br/> <br/> [Organisation Data Service - ORD API](https://digital.nhs.uk/developer/api-catalogue/organisation-data-service-ord) <br/> <br/> [Organisation Data Service](https://digital.nhs.uk/services/organisation-data-service#access-our-data) | A formally or informally recognized grouping of people or organizations formed for the purpose of achieving some form of collective action. Includes companies, institutions, corporations, departments, community groups, healthcare practice groups, payer/insurer, etc.|
| Location {{link:http://hl7.org/fhir/StructureDefinition/Location}} | {{pagelink:NHSDigital-Location-duplicate-2}}  | 	Details and position information for a physical place where services are provided and resources and participants may be stored, found, contained, or accommodated. |
| Practitioner {{link:http://hl7.org/fhir/StructureDefinition/Practitioner}} | {{pagelink:NHSDigital-Practitioner}}  | [Organisation Data Service](https://digital.nhs.uk/services/organisation-data-service#access-our-data)  |A person who is directly or indirectly involved in the provisioning of healthcare. |
| PractitionerRole {{link:http://hl7.org/fhir/StructureDefinition/PractitionerRole}}| {{pagelink:NHSDigital-PractitionerRole}}  | [Spine Directory Service - LDAP API](https://digital.nhs.uk/developer/api-catalogue/spine-directory-service-ldap) | A specific set of Roles/Locations/specialties/services that a practitioner may perform at an organization for a period of time. |
| HealthcareService {{link:http://hl7.org/fhir/StructureDefinition/HealthcareService}}	| {{pagelink:NHSDigital-HealthcareService}}  | [Directory of Services - Urgent and Emergency Care - REST API](https://digital.nhs.uk/developer/api-catalogue/directory-of-services-urgent-and-emergency-care-rest) <br/> <br/> [Electronic Prescription Service Directory of Services API](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-directory-of-services) |	The details of a healthcare service available at a location. |
| Endpoint {{link:http://hl7.org/fhir/StructureDefinition/Endpoint}} | {{pagelink:SDS-Endpoint}}  | [Spine Directory Service - LDAP API](https://digital.nhs.uk/developer/api-catalogue/spine-directory-service-ldap) <br/> <br/> [Spine Directory Service - FHIR API](https://digital.nhs.uk/developer/api-catalogue/spine-directory-service-fhir) | The technical details of an endpoint that can be used for electronic services, such as for web services providing XDS.b or a REST endpoint for another FHIR server. This may include any security context information. |

{{render:Diagams-administration-module-prov-dir}}

<br/>

### Scheduling and Appointments 

The Scheduling/Appointment resources permit the planning of encounters to occur and follow on with other clinical activities.

| Name	| NHS (England) or UK Profile | API or Registry	Description |
|--
| Schedule {{link:http://hl7.org/fhir/StructureDefinition/Schedule}}	| [UKCoreSchedule](link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Schedule) | [Booking and Referral - FHIR API](https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir) |A container for slots of time that may be available for booking appointments. |
|Slot {{link:http://hl7.org/fhir/StructureDefinition/Slot}}| [UKCore-Slot](link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot) | [Booking and Referral - FHIR API](https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir) |	A slot of time on a schedule that may be available for booking appointments. |
|Appointment {{link:http://hl7.org/fhir/StructureDefinition/Appointment}} |[UKCore-Appointment](link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment) | [Booking and Referral - FHIR API](https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir) |	A booking of a healthcare event among patient(s), practitioner(s), related person(s) and/or device(s) for a specific date/time. This may result in one or more Encounter(s). |
| AppointmentResponse {{link:http://hl7.org/fhir/StructureDefinition/AppointmentResponse}} | | [Booking and Referral - FHIR API](https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir) |	A reply to an appointment request for a patient and/or practitioner(s), such as a confirmation or rejection. |

{{render:Diagams-administration-module-scheduling}}

#### Related Standards

| Type | Description |
|--
| Appointment Notification Events | For PAS events see ADT_A05 in [HSCIC ITK HL7 V2 Message Specifications](https://github.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/blob/master/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf) |

<br/>

### Clinical Categorisation Resources 

Most clinical activities occur grouped in some way. Long term care is typically covered by an EpisodeOfCare, whereas short term care is covered by encounters. Account associates the tracking of transactions back to a Patient (or other resource). Flag is just used to highlight a warning or other notification about a patient (or other resource)

| Name | NHS (England) or UK Profile | Alias |Description |
|--
| EpisodeOfCare {{link:http://hl7.org/fhir/StructureDefinition/EpisodeOfCare}} | [EpisodeOfCare](https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare) | Case Program |Problem	An association between a patient and an organisation / healthcare provider(s) during which time encounters may occur. The managing organisation assumes a level of responsibility for the patient during this time. |
|Encounter {{link:http://hl7.org/fhir/StructureDefinition/Encounter}} | [UKCore-Encounter](link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter) |Visit |An interaction between a patient and healthcare provider(s) for the purpose of providing healthcare service(s) or assessing the health status of a patient. |
| Account {{link:http://hl7.org/fhir/StructureDefinition/Account}} | | Cost centre | A financial tool for tracking value accrued for a particular purpose. In the healthcare field, used to track charges for a patient, cost centers, etc. |
| Flag {{link:http://hl7.org/fhir/StructureDefinition/Flag}} |[UKCore-Flag](link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Flag) | Barriers to Care, Alert |Prospective warnings of potential issues when providing care to the patient. |

{{render:Diagams-administration-module-interactions}}

#### Related Standards

|Type |Description |
| 
| Encounter Notification Events	| For PAS events see ADT_A01, ADT_A02, ADT_A03, ADT_A04, etc in [HSCIC ITK HL7 V2 Message Specifications](https://github.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide/blob/master/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf) |