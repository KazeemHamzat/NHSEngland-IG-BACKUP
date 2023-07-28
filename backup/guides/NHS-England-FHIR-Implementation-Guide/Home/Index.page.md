# Home 

This NHS England FHIR Implementation Guide provides additional guidance, rules and constraints which extends the [UK Core Implementation Guide](https://simplifier.net/guide/hl7fhirukcorer4release1/home). 

The scope of this guide is NHS England, it also contains English NHS rules and constraints which are documented in Level 3 - 
{{pagelink:Administration}}

---

## Level 1 - Foundation

Basic framework on which the specification is built.
See NHS England FHIR {{pagelink:Policy}} for more details.

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
    <a>England-CapabilityStatement</a>
    </td>
    <td>
 {{pagelink:Profile-England-Provenance, text:England-Provenance}}
    </td>
    <td>
 {{pagelink:Profile-England-MessageHeader, text:England-MessageHeader}} 
    </td>
   </tr>
    <tr>
     <td>
     {{pagelink:Profile-England-OperationOutcome, text:England-OperationOutcome}}
     </td>
     <td>
     Consent
     </td>
     <td>
   England-Bundle
     </td>
   </tr>
    <tr>
     <td>
England-OperationDefinition
     </td>
     <td>
     AuditEvent
     </td>
     <td>
   England-MessageDefinition
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
   <tr>
     <td>
       England-Encounter
     </td>
     <td>
       England-Appointment 
     </td>
     <td>
  England-Flag
     </td>
   </tr>
   <tr>
     <td>
      England-SDS-Device
     </td>
     <td>
    England-SDS-Endpoint
     </td>
     <td>
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
     <th width="33%">{{pagelink:Diagnostics}}</th>
     <th width="33%">{{pagelink:Medications}} </th>
     <th width="33%">{{pagelink:Workflow}} </th>
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
{{pagelink:Profile-England-MedicationDispense, text:England-MedicationDispense}}
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
    England-ImmunizationRecommendation
    </td>
    <td>
    </td>
    <td>
    </td>
   </tr>
    <tr>
    <td>
    </td>
    <td>
    </td>
    <td></td>
   </tr>
   </tbody>
</table>

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
    England-Composition
    </td>
     <td>
     England-Questionnaire
    </td>
    <td>
 England-Claim
    </td>
   </tr>
   <tr>
    <td>
       England-DocumentReference
    </td>
    <td>
    England-CommunicationRequest
    </td>
    <td>
    </td>
   </tr>
   </tbody>
</table>

---

### Related Guides

<div class="nhsd-o-card-list">
    <div class="nhsd-t-grid">
        <div class="nhsd-t-row nhsd-o-card-list__items ">
         <!-- UK Core -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2?version=1.1.3" class="nhsd-a-box-link " aria-label="Read the EPS Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">UK Core </h1>
                                    <p class="nhsd-t-body-s">UK Core FHIR Guidance</p>
                                </div>
                                <div class="nhsd-m-card__button-box">
                                    <span class="nhsd-a-button nhsd-a-button--invert">
                                        <span class="nhsd-a-button__label">Find out more</span>
                                    </span>
                                </div>
                            </div>
                        </div>
                    </a>
                </article>
            </div>
            <!-- API Catalogue -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://digital.nhs.uk/developer/api-catalogue" class="nhsd-a-box-link " aria-label="View the NHS Digital API Catalogue">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">NHS Digital API Catalogue</h1>
                                    <p class="nhsd-t-body-s">API's which use the NHS Digital Implementation Guide</p>
                                </div>
                                <div class="nhsd-m-card__button-box">
                                    <span class="nhsd-a-button nhsd-a-button--invert">
                                        <span class="nhsd-a-button__label">Find out more</span>
                                    </span>
                                </div>
                            </div>
                        </div>
                    </a>
                </article>
            </div>
           
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/NHSDigital-Medicines" class="nhsd-a-box-link " aria-label="Read the NHS Digital EPS Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">NHS Medications (EPS)</h1>
                                    <p class="nhsd-t-body-s">NHS Electronic Prescribing Service</p>
                                </div>
                                <div class="nhsd-m-card__button-box">
                                    <span class="nhsd-a-button nhsd-a-button--invert">
                                        <span class="nhsd-a-button__label">Find out more</span>
                                    </span>
                                </div>
                            </div>
                        </div>
                    </a>
                </article>
            </div>
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/nhsbookingandreferralstandard" class="nhsd-a-box-link " aria-label="Read the NHS Digital BARS Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">NHS Workflow (BARS)</h1>
                                    <p class="nhsd-t-body-s">NHS Booking and Referrals Standard</p>
                                </div>
                                <div class="nhsd-m-card__button-box">
                                    <span class="nhsd-a-button nhsd-a-button--invert">
                                        <span class="nhsd-a-button__label">Find out more</span>
                                    </span>
                                </div>
                            </div>
                        </div>
                    </a>
                </article>
            </div>
        </div>
    </div>
</div>



<br>
