### Profiling

 <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Work in progress</div>

NHS Digital will derive any profiles from the UK Core profiles where these exist (see requirement FHIR-NAT-02 {{pagelink:NationalServices-duplicate-2}})

In addition, the following requirements have been agreed:
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-PROFILE-01:</b>

<br/>
<br/>

- Profiles <b>MUST NOT</b> define alternate summary fields for resources.

<br/>
<br/>

All FHIR base resources have a number of fields defined as 'summary' fields, which appear in results when the client requested summary versions of the resource to be returned (for example in search results). These summary fields can only be defined in base resources and cannot be changed in any profiles.

**Note:** This is a rule established by HL7, but is not clear in the HL7 FHIR specification.