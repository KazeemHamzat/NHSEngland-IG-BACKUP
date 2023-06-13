## NHSDigital-Composition

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Experimental. This page is for illustration of a concept</div>

| Conformance url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Composition](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Composition) |  

This FHIR R4 profile is designed to set a core Composition standard for:

- Transfer of Care ITK3 and STU3 Digital Meds
- [Summary Care Record](https://digital.nhs.uk/developer/api-catalogue/summary-care-record-fhir)
- GP Connect unstructured record


<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
       <!-- <li role="presentation" >
            <a href="#Combined" role="tab" data-toggle="tab">Combined</a>
        </li> -->
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab" class="active">Differential</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
       
     <!--   <div id="Combined" role="tabpanel" class="tab-pane">
            <br>
  with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Composition, snapshot}}
        </div> -->
         <div id="Differential" role="tabpanel" class="tab-pane active">
            <br>
 from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Composition, diff}}
        </div>
<div id="Examples"  class="tab-pane">



</div>
</div>


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
identifier
    </td>
    <td>
 token
    </td>
     <td>
Version-independent identifier for the Composition
    </td>
    <td>
SHALL
    </td>
    <td>
Composition.identifier
    </td>
   </tr>  
   </tbody>
</table>

<br> 

Additional parameters can be on <a href="https://www.hl7.org/fhir/composition.html#search" target="_blank">Composition - Search Parameters</a>

<a name="mandatorysearch"></a>
### Mandatory Search Parameters

None defined

<a name="optionalsearch"></a>
### Optional Search Parameters

#### identifier

**SHOULD** support searching using the `identifier` search parameter.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Composition?identifier={system|}[code]    
</div>

Example:

`GET [baseUrl]/Composition?identifier=FA60BE64-1F34-11EB-A2A8-000C29A364EB`

Return all Composition resources for an identifier FA60BE64-1F34-11EB-A2A8-000C29A364EB.
