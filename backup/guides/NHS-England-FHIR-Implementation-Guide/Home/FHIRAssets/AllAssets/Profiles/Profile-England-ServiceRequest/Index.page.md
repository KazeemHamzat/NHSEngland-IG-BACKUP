---
topic: Profile-England-ServiceRequest
---

# StructureDefinition-England-ServiceRequest

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandServiceRequest'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'EnglandServiceRequest'
select
	Profile_Purpose: purpose
```


<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, snapshot}}
</div>



<div id="Examples" class="tabcontent">
<br>
  <h3>Examples</h3>
  <b>ServiceRequest</b> -An example to illustrate a cancer screening centre service within a HealthcareService resource

<br>{{pagelink:Example-England-HealthcareService-CancerScreeningCentre}}
<br><br>

  <b>ServiceRequest</b> - An example to illustrate a ERS search results service within a HealthcareService resource.


<br>{{pagelink:Example-England-HealthcareService-ERSSearchResults}}
<br><br>
</div>
</nocheck>



<div id="Examples" class="tabcontent">
<br>
  <h3>Examples</h3>
  
Some examples to illustrate ServiceRequest

<br>
<br> {{pagelink:ServiceRequest-BARS}}
<br>
<br>{{pagelink:ServiceRequest-ERS}}
<br>
<br>{{pagelink:ServiceRequest-Active-ERS-Advice-And-Guidance}}
<br>
<br>{{pagelink:ServiceRequest-Active-Patient-Referral}}
<br>
<br>{{pagelink:ServiceRequest-Draft-ERS-Advice-And-Guidance}}
<br>
<br>{{pagelink:ServiceRequest--Draft-Patient-Referral}}
<br>
<br> {{pagelink:ServiceRequest-ERS-Counselling}}
<br>
<br>{{pagelink:ServiceRequest-ERS-Portal-Link}}
<br>
<br> {{pagelink:ServiceRequest-ERS-WayFinder}}
<br>
<br>{{pagelink:ServiceRequest-Referral-FollowUp-Advice}}
</div>
</nocheck>
<br>

---

## Profile Specific Implementation Guidance: ##

---