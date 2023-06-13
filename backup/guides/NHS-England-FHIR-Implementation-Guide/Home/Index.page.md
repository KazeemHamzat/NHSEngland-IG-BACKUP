# Home 

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: This is version 2.8.0. For a full list of available versions, see the <a href="https://simplifier.net/guide/NHSDigital/Home/HelpandSupport/Directory">directory</a> of published versions
</div>


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
 
<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th width="25%">Conformance</th>
     <th width="25%">Security</th>
     <th width="25%">Other</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
   {{pagelink:NHSDigital-CapabilityStatement}}   
    </td>
    <td>
 {{pagelink:NHSDigital-Provenance}}
    </td>
    <td>
 {{pagelink:NHSDigital-Bundle}}      
    </td>
   </tr>
    <tr>
     <td>
     {{pagelink:NHSDigital-MessageDefinition}} 
     </td>
     <td>
     Consent
     </td>
     <td>
   {{pagelink:NHSDigital-MessageHeader}} 
     </td>
   </tr>
    <tr>
     <td>
{{pagelink:NHSDigital-OperationDefinition}} 
     </td>
     <td>
     AuditEvent
     </td>
     <td>
  {{pagelink:NHSDigital-OperationOutcome}} 
     </td>
   </tr>
   </tbody>
</table>

---

## Level 3 - Administration

Linking to real world concepts in the healthcare system. 
See {{pagelink:Administration}} for more details.

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th width="25%">Individuals</th>
     <th width="25%">Entities</th>
     <th width="25%">Management</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
      {{pagelink:NHSDigital-Patient}} 
    </td>
    <td>
        {{pagelink:NHSDigital-Location}}  
    </td>
     <td>
      {{pagelink:NHSDigital-Appointment}}
    
     </td>
   </tr>
   <tr>
    <td>
      {{pagelink:NHSDigital-Practitioner}} 
   </td>
   <td>
      {{pagelink:NHSDigital-Organization}}
   </td>
      <td>
        {{pagelink:NHSDigital-Encounter}}
     </td>
   </tr>
   <tr>
     <td>
       {{pagelink:NHSDigital-PractitionerRole}} 
     </td>
     <td>
      {{pagelink:NHSDigital-HealthcareService}}  
     </td>
     <td>
  {{pagelink:NHSDigital-Flag}}
     </td>
   </tr>
   <tr>
     <td>
     </td>
     <td>
     {{pagelink:SDS-Device}} 
     </td>
     <td>
     </td>
   </tr>
   <tr>
     <td>
     </td>
     <td>
      {{pagelink:SDS-Endpoint}}
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

<table class="regular nhsd-!t-margin-bottom-6" style="width:100%">
 <thead>
   <tr>
     <th width="25%">{{pagelink:Diagnostics}}</th>
     <th width="25%">{{pagelink:Medications}} </th>
     <th width="25%">{{pagelink:Workflow}} </th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
       {{pagelink:NHSDigital-Observation}}
    </td>
    <td>
{{pagelink:NHSDigital-Immunization}}  
    <td>
{{pagelink:NHSDigital-ServiceRequest}}  
    </td>
   </tr>
   <tr>
    <td>
{{pagelink:NHSDigital-QuestionnaireResponse}}
    </td>
    <td>
    <a href="https://simplifier.net/guide/NHSDigital-Medicines/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-MedicationRequest">NHSDigital-MedicationRequest</a>
    </td>
    <td>
 {{pagelink:NHSDigital-Task}} 
    </td>
   </tr>
   <tr>
    <td>
    </td>
    <td>
    <a href="https://simplifier.net/guide/NHSDigital-Medicines/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-MedicationDispense">NHSDigital-MedicationDispense</a>
    </td>
    <td>
    </td>
   </tr>
     <tr>
    <td>
    </td>
    <td>
{{pagelink:NHSDigital-ImmunizationRecommendation}}
    </td>
    <td></td>
   </tr>
   </tbody>
</table>

<table class="regular nhsd-!t-margin-bottom-6" style="width:100%">
 <thead>
   <tr>
     <th width="25%">Document</th>
     <th width="25%">Definitional Artifacts</th>
       <th width="25%">Other</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
       {{pagelink:NHSDigital-Composition}}
    </td>
     <td>
     {{pagelink:NHSDigital-Questionnaire}}
    </td>
    <td>
 <a href="https://simplifier.net/guide/NHSDigital-Medicines/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Claim">NHSDigital-Claim</a>
    </td>
   </tr>
   <tr>
    <td>
       {{pagelink:NHSDigital-DocumentReference}}
    </td>
    <td>
    </td>
    <td>
      {{pagelink:NHSDigital-CommunicationRequest}}       
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
                    <a href="https://simplifier.net/guide/UKCoreImplementationGuide0.2.0STU1/Home" class="nhsd-a-box-link " aria-label="Read the EPS Guidance">
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
