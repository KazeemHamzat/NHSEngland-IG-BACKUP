# Home 

This NHS England FHIR Implementation Guide provides additional guidance, rules and constraints which extends the [UK Core Implementation Guide](https://simplifier.net/guide/hl7fhirukcorer4release1/home). 

The scope of this guide is NHS England, it also contains English NHS rules and constraints which are documented in Level 3 - 
{{pagelink:Administration}}

---

## Level 1 - Foundation

Basic framework on which the specification is built.
See NHS England FHIR <a href='https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home?version=current'>Policy</a> for more details.

---

## Level 2 - Implementation Support

Supporting implementation and binding to external specifications, covering: 
{{pagelink:FHIR-Validation}}
, {{pagelink:Guidance-Exchange}} and Exchange Patterns. 

See {{pagelink:Implementation-Support}} for more details.
 
<table class="regular assets" style="width:100%">
 <thead>
   <tr>
     <th width="33%">Conformance</th>
     <th width="33%">Security</th>
     <th width="33%">Other</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
    </td>
    <td>
    </td>
    <td>
 {{pagelink:Profile-England-MessageHeader, text:England-MessageHeader}} 
    </td>
   </tr>
    <tr>
    <td>
    </td>
    <td>
    </td>
    <td>
 {{pagelink:Profile-England-OperationOutcome, text:England-OperationOutcome}} 
    </td>
   </tr>
   </tbody>
</table>

---

## Level 3 - Administration

Linking to real world concepts in the healthcare system. 
See {{pagelink:Administration}} for more details.

<table class="regular assets" style="width:100%">
 <thead>
   <tr>
     <th width="33%">Individuals</th>
     <th width="33%">Entities</th>
     <th width="33%">Management</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
      {{pagelink:Profile-England-Patient,text:England-Patient}} 
    </td>
    <td>
        {{pagelink:Profile-England-Location,text:England-Location}}  
    </td>
     <td>
      {{pagelink:Profile-England-Practitioner,text:England-Practitioner}} 
    
     </td>
   </tr>
   <tr>
    <td>
      {{pagelink:Profile-England-Organization,text:England-Organization}}
   </td>
   <td>
         {{pagelink:Profile-England-PractitionerRole,text:England-PractitionerRole}} 
   </td>
      <td>
        {{pagelink:Profile-England-HealthcareService,text:England-HealthcareService}}
     </td>
   </tr>
   </tbody>
</table>

---

## Level 4 - Record Keeping and Data Exchange

Record-keeping and Data Exchange for the healthcare process. See also NHS Digital 
{{pagelink:Workflow}} 
and {{pagelink:Medications}} supplements.

<table class="regular assets" style="width:100%">
 <thead>
   <tr>
     <th width="33%">Diagnostics</th>
     <th width="33%">Medications </th>
     <th width="33%">Workflow </th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
       {{pagelink:Profile-England-Observation, text:England-Observation}}
    </td>
    <td>
{{pagelink:Profile-England-Immunization, text:England-Immunization}}  
    <td>
{{pagelink:Profile-England-ServiceRequest, text:England-ServiceRequest}}  
    </td>
   </tr>
   <tr>
    <td>
    </td>
    <td>
     {{pagelink:Profile-England-MedicationRequest, text:England-MedicationRequest}}
    
    </td>
    <td>
 {{pagelink:Profile-England-Task, text:England-Task}} 
    </td>
   </tr>
   <tr>
    <td>
    </td>
    <td>
     {{pagelink:Profile-England-MedicationDispense, text:England-MedicationDispense}}
    
    </td>
    <td>
    </td>
   </tr>
   </tbody>
</table>
<br>
<table class="regular assets nhsd-!t-margin-bottom-6" style="width:100%">
 <thead>
   <tr>
     <th width="33%">Document</th>
     <th width="33%">Definitional Artifacts</th>
     <th width="33%">Other</th>
   </tr>
 </thead>
 <tbody>
   <tr>
   <td>
     The scope of this guide does not currently cover FHIR Document 
        composition.
    </td>
    </tr>
   </tbody>
</table>

---
