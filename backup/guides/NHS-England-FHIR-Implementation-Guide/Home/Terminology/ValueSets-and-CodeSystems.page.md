---
topic: ValueSetsAndCodeSystems
---
## ValueSets and Code Systems

This is the list of ValueSets and CodeSystems defined for use within the NHS England Implementation Guide.

Other ValueSets are usable if the binding strength is defined as extensible.
<br>Additional guidance is available on <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/Terminology/ValueSetsandCodeSystems.page.md?version=current" target="_blank">UK Core ValueSets and CodeSystems</a> index page.
<br><br>

<style>
 [class*=override] {
 	background-color:#f2f2f2;
	 }
</style>

<div id="Narrative" class="tabcontent"  style="display:block">
<table id="valuesetlist">
<tr>
<th width="50%">ValueSet</th>
<th width="5%">Status</th>
<th width="40%">Bound in Profile/Extension</th>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ClinicalSpecialty}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-HealthcareService}}</td>
</tr>
<tr>
<td colspan="4">{{pagelink:CodeSystem-England-ClinicalSpecialty}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ERSSpecialty}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-HealthcareService}}</td>
</tr>
<tr>
<td colspan="4">{{pagelink:CodeSystem-England-ClinicalSpecialty}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ERSClinicType}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-HealthcareService}}</td>
</tr>
<tr>
<td colspan="4">{{pagelink:CodeSystem-England-ERSClinicType}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ImmunizationExplanationReason}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Immunization}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ReasonImmunizationNotAdministered}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Immunization}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-VaccineCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Immunization}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-LocationType}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Location}}</td>
</tr>
<tr>
<td colspan="4">{{pagelink:CodeSystem-England-OrganisationRole}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-DMMedicationDispenseStatusReason}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-MedicationDispense}}</td>
</tr>
<tr>
<td colspan="4">{{pagelink:CodeSystem-England-MedicationDispenseStatusReason}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-DMTaskReasonCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-MedicationDispense}}</td>
</tr>
<tr>
<td colspan="4">{{pagelink:CodeSystem-England-EPSTaskDispenseReturnStatusReason}}</td>
</tr>
<tr>
<td colspan="4">{{pagelink:CodeSystem-England-EPSTaskDispenseWithdrawReason}}</td>
</tr>
<tr>
<td colspan="4">{{pagelink:CodeSystem-England-MedicationRequestStatusReason}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-MedicationCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-MedicationDispense}},{{pagelink:Profile-England-MedicationRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk where parent Equal VTM</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk where parent Equal VMP</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk where parent Equal AMP</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk where parent Equal VMPP</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk where parent Equal AMPP</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>


<tr>
<td>{{pagelink:ValueSet-England-DMMedicationDispenseType}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-MedicationDispense}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-MedicationDispenseType}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-DMMedicationRequestStatusReason}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-MedicationRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-MedicationRequestStatusReason}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-DMMedicationRequestCategory}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-MedicationRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-MedicationRequestCategory}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/medicationrequest-category</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-DMMedicationRequestCourseOfTherapy}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-MedicationRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-MedicationRequestCourseOfTherapy}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-MessageEvents}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-MessageHeader}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-MessageEventEPS}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-MessageEventBARS}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-OperationOutcomeCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-OperationOutcome}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-SpineErrorOrWarningCode}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-EPSIssueCode}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-APIErrorOrWarningCode}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-HTTPErrorCode}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-ERSErrorCode}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ObservationCategory}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Observation}}</td>
</tr>
<tr>
<td colspan="4">Composed of <code>http://terminology.hl7.org/CodeSystem/v3-ObservationCategory</code></td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-CovidTestPillar}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-OrganisationRole}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Organization}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-OrganisationRole}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-PractitionerRoleCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-PractitionerRole}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-SDSJobRoleCode}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-BARSMessageServiceRequestCategory}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-ServiceRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-BARSMessageServiceRequestCode}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ServiceRequestCategory}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-ServiceRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ServiceRequestCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-ServiceRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-ServiceRequestCode}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-CareSettingType}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-ServiceRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-NHSDataModelAndDictionaryTreatmentFunction}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-NHSDataModelAndDictionaryTreatmentFunctionCategory}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-ServiceRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-NHSDataModelAndDictionaryTreatmentFunction}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ERSSpecialty}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-ServiceRequest}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-England-ERSSpecialty}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-ActionCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Task}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-TaskCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Task}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://hl7.org/fhir/CodeSystem/task-code</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td>{{pagelink:ValueSet-England-WorkflowCode}}</td>
<td>draft</td>
<td>{{pagelink:Profile-England-Task}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem {{pagelink:Profile-England-Task}}ValueSet-England-WorkflowCode</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

</table>
</div>
