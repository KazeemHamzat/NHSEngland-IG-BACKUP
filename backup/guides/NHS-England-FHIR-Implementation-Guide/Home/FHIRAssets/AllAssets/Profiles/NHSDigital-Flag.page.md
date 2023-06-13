## NHSDigital-Flag

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Experimental. This page is for illustration of a concept</div>

| Conformance url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Flag](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Fla) |  

This FHIR R4 profile is designed to set a core Flag standard for:

- FGM
- CPIS
- Reasonable Adjustments

---

- <a href="#search">Search Parameters</a>
  - <a href="#mandatorysearch">Mandatory Search Parameters</a>
  - <a href="#optionalsearch">Optional Search Parameters</a>


<a name="search"></a>
## Search Parameters


<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="15%">Name</th>
     <th data-no-sort width="15%">Type</th>
     <th data-no-sort width="35%">Description</th>
      <th data-no-sort width="15%">Conformance</th>
       <th data-no-sort width="20%">Path</th>
   </tr>
 </thead>
 <tbody>    
    <tr>
    <tr>
    <td>
 patient:identifier
    </td>
    <td>
 token
    </td>
     <td>
The identity of a subject to list flags for
    </td>
    <td>
SHALL
    </td>
    <td>
Flag.subject.where(resolve() is Patient)
(Patient)
    </td>
   </tr>  
   </tbody>
</table>

<br> 

Additional parameters can be on <a href="https://www.hl7.org/fhir/flag.html#search" target="_blank">Flag - Search Parameters</a>

<a name="mandatorysearch"></a>
### Mandatory Search Parameters

#### patient:identifier

**SHALL** support searching using the `patient:identifier` search parameter.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Flag?patient:identifier={system|}[code]    
</div>

Example:

`GET [baseUrl]/Flag?patient:identifier=9876543210`

Return all Flag resources for a Patient with an identifier 9876543210.


<a name="optionalsearch"></a>
### Optional Search Parameters

None defined