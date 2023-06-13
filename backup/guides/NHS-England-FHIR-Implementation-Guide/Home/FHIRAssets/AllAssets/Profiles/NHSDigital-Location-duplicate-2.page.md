## {{page-title}}

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Location](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Location) | | draft |

A Location includes both incidental locations (a place which is used for healthcare without prior designation or authorisation) and dedicated, formally appointed locations. Locations may be private, public, mobile or fixed and scale from small freezers to full hospital buildings or parking garages.

<br>

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation"  class="active">
            <a href="#Combined" role="tab" data-toggle="tab">Combined</a>
        </li>
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab">Differential</a>
        </li>
         <li role="presentation">
            <a href="#Constraints" role="tab" data-toggle="tab">Constraints</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
       
        <div id="Combined" role="tabpanel" class="tab-pane active">
            <br>
     {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Location, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
   {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Location, diff}}
        </div>
         <div id="Constraints"  class="tab-pane">
<br/>
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Location'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples"  class="tab-pane">
<br/>
- {{pagelink:RBA11}}

</div>
</div>

---

- <a href="#search">Search Parameters</a>
  - <a href="#mandatorysearch">Mandatory Search Parameters</a>
  - <a href="#optionalsearch">Optional Search Parameters</a>
  

  <a name="search"></a>
## Search Parameters


The following search parameters and search parameter combinations **SHALL** be supported.:

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
    <td>
address-postcode 
    </td>
    <td>
  string
    </td>
     <td>
A postalCode specified in an address
    </td>
    <td>
MAY
    </td>
    <td>
Location.address.postalCode
    </td>
   </tr>
    <tr>
    <td>
identifier 
    </td>
    <td>
  token
    </td>
     <td>
Any identifier for the location (e.g. SDS/ODS code)
    </td>
    <td>
MAY
    </td>
    <td>
Location.identifier
    </td>
   </tr>
   </tbody>
</table>

<br> 

Additional parameters can be on <a href="https://www.hl7.org/fhir/location.html#search" target="_blank">Location - Search Parameters</a>

<a name="mandatorysearch"></a>
### Mandatory Search Parameters

None

<a name="optionalsearch"></a>
### Optional Search Parameters

#### address-postcode

**MAY** support searching by the `address-postcode` search parameter:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Location?address-postcode=[address-postcode] 
</div>

Example: 

`GET [baseUrl]/Location?address-postcode=NG10%201RY`

Return all Location resources with Post Code of NG10 1RY.

#### identifier (SDS/ODS Code)

**MAY** support searching by the `identifier` search parameter:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Location?identifier={system|}[code]  
</div>

Example:

`GET [baseUrl]/Location?identifier=https://fhir.nhs.uk/Id/ods-site-code|RTG08`

Return all Location resources with NHS Trust Site of RTG08 (Long Eaton Clinic).
