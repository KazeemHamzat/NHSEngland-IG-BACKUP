### National Services

 <div markdown="span" class="alert alert-warning" role="alert">
 <i class="fas fa-exclamation-triangle"></i><b> Important:</b> Work in progress</div>

In addition to the general requirements for the use of FHIR nationally, there are also some specific requirements for the national services delivered by NHS Digital or other national organisations that use FHIR APIs.

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> FHIR-NAT-01:</b>

<br/>
<br/>

- National FHIR resources <b>MUST</b> use consistent basePaths.

<br/>
<br/>

In order to support the move to FHIR across a range of national services, there is a need to define a URL scheme which will allow entities such as Patients and Organisations to be referenced reliably even when the relevant national FHIR services have not yet been implemented. These URLs should also support a future move to Internet-facing services, and as such it should be possible to resolve them over both the Internet and N3/HSCN as applicable.

The basePaths SHOULD be used for national services where possible:

<table class="regular assets">
<thead>
<tr>
<th>API Name</th>
<th>Base Path</th>
<th>Further path to endpoints</th>
</tr>
</thead>
<tbody>
<tr>
<td>Personnel Demographics Service</td>
<td>/personnel-demographics</td>
<td>/FHIR/R4</td>
</tr>
<tr>
<td>Electronic Prescription Service</td>
<td>/electronic-prescriptions</td>
<td>/FHIR/R4</td>
</tr>
<tr>
<td>Spine Directory Services (SDS) API</td>
<td>/spine-directory</td>
<td>/FHIR/R4</td>
</tr>
<tr>
<td>COVID-19 Test Results API</td>
<td>/covid-19-test-result</td>
<td>/FHIR/R4</td>
</tr>
<tr>
<td>Immunisation History API</td>
<td>/immunisation-history</td>
<td>/FHIR/R4</td>
</tr>
</tbody>
</table>

**IMPORTANT NOTE**: This requirement is to promote alignment across NHS Digital, but until individual services are developed there is still a risk that these URLs may change.

</div>
<br/>

