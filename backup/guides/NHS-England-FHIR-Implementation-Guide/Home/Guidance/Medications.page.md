## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS Digital</div>

This module is concerned with resources and functionality in 2 main domains:

- The ordering, dispensing, administration of medications and recording statements of medication use.
- Recording of Immunizations given (or not given).


### Medications 

| Name| NHS Digital (or UKCore) Profile |	API |	Description |
|--
| {{link:http://hl7.org/fhir/StructureDefinition/MedicationRequest}} |	{{link:https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest}}	| [Electronic Prescription Service - FHIR API](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir) | Represents an instruction for the administration of medication to a patient - both in the inpatient (hospital) and community setting. It can also include instructions for the dispensing, the reasons why the administration should occur and other data. <br/> It is called an 'Request' to be consistent with other FHIR resources and the workflow pattern, but a common alias for this resource is a 'Prescription' or an 'Order'. The Order itself represents the content of the instruction and is not, by itself, actionable. The workflow process around 'fulfilling' the order is part of the generic FHIR workflow (see below), with the MedicationRequest representing the contents. |
| {{link:http://hl7.org/fhir/StructureDefinition/MedicationDispense}} | {{link:https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense}}	| [Electronic Prescription Service - FHIR API](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir) | The provision of a supply of a medication with the intention that it is subsequently consumed by a patient (usually in response to a prescription). |
| {{link:http://hl7.org/fhir/StructureDefinition/MedicationAdministration}} | {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration}} | |	A record of a patient actually consuming a medicine, or if it has otherwise been administered to them |
| {{link:http://hl7.org/fhir/StructureDefinition/MedicationStatement}} | {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement}}	| | This is a record indicating that a patient may be taking a medication now, has taken the medication in the past, or will be taking the medication in the future. The source for this information can be the patient, significant other (such as a family member or spouse), or a clinician. A common scenario where this information is captured is during the history taking process during a patient visit or stay. A medication statement is not a part of the prescribe->dispense->administer sequence, but is a report that such a sequence (or at least a part of it) did take place, resulting in a belief that the patient has received a particular medication. It may be used to construct a patients 'Current Medications' list. |
| {{link:http://hl7.org/fhir/StructureDefinition/Medication}} | {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication}}	| | The medication resource represents an actual medication that can be given to a patient, and referenced by the other medication resources. In many cases, this resource is not needed and the drug is indicated by a reference to the appropriate terminology and so can be represented using a codeable concept. In other cases, however, it may be desired to indicate more details than the simple drug (such as the packaging, whether it is a generic medication or the active and inactive ingredients) and so the Medication resource can be used for this. |


### Immunizations


| Name | NHS Digital (or UKCore) Profile | API | Description |
|--
| {{link:http://hl7.org/fhir/StructureDefinition/Immunization}} | {{link:https://fhir.nhs.uk/StructureDefinition/England-Immunization}}	| [Immunisation History - FHIR API](https://digital.nhs.uk/developer/api-catalogue/immunisation-history-fhir) <br/> [Vaccination](https://digital.nhs.uk/developer/api-catalogue/vaccination) | The Immunization resource is intended to cover the recording of current and historical administration of vaccines to patients across all healthcare disciplines in all care settings and all regions. This includes immunization of both humans and animals, but does not include the administration of non-vaccine agents, even those that may have or claim to have immunological effects. |
| {{link:http://hl7.org/fhir/StructureDefinition/ImmunizationRecommendation}}	| | |A patient's point-in-time immunization and recommendation (i.e. forecasting a patient's immunization eligibility according to a published schedule) with optional supporting justification |