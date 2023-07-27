### National Services

 <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Work in progress</div>

In addition to the general requirements for the use of FHIR nationally, there are also some specific requirements for the national services delivered by NHS Digital or other national organisations that use FHIR APIs.

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-NAT-01:</b>

<br/>
<br/>

- National FHIR resources <b>MUST</b> use consistent basePaths.

<br/>
<br/>

In order to support the move to FHIR across a range of national services, there is a need to define a URL scheme which will allow entities such as Patients and Organisations to be referenced reliably even when the relevant national FHIR services have not yet been implemented. These URLs should also support a future move to Internet-facing services, and as such it should be possible to resolve them over both the Internet and N3/HSCN as applicable.

The basePaths SHOULD be used for national services where possible:

| API Name | Base Path | Further path to endpoints | 
|--
| Personnel Demographics Service | /personnel-demographics | /FHIR/R4 |
| Electronic Prescription Service | /electronic-prescriptions | /FHIR/R4 |
| Spine Directory Services (SDS) API | /spine-directory | /FHIR/R4 |
| COVID-19 Test Results API | /covid-19-test-result | /FHIR/R4 |
| Immunisation History API | /immunisation-history | /FHIR/R4 |

**IMPORTANT NOTE**: This requirement is to promote alignment across NHS Digital, but until individual services are developed there is still a risk that these URLs may change.

</div>
<br/>

