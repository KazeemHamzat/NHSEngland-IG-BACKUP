## {{page-title}}

Each Profile SHALL consist of multiple pages, all residing within a folder that SHALL be named <code>Profile-England-[profile]</code>. This folder SHALL reside withinin the folder 'Profiles and Extensions'.

The pages within the folder SHALL follow the structure: 
- Index (mandatory) 
- Extensions (optional) 
- Bindings (differential) (optional) 
- Constraints (differential) (optional) 
- <i>[Profile Element name]</i> (multiple) (optional) 

## Index Page 

Unless stated as optional, the index page SHALL have, in order, the following: 
- Topic 
- Structure Definition 
- Profile Purpose 
- A profile table with the following views: 
  - Snapshot 
  - Differential 
  - Hybrid 
  - XML snapshot 
  - JSON snapshot 
  - Examples
- Example Usage Scenarios
- Profile Specific Implementation Guidance  
- Minimum Viable Content

---

## Topic

A profile index page should have a YAML header:
- a `topic`, which allows the page to be referenced using \{ \{pagelink:[topic]\}\} within the IG. 

A YAML header SHALL be the first item on a page, it SHALL be unique, and it SHALL be in the following format: 

~~~html
---
topic: [Section]-[ResourceName]
---
~~~

Example Topics:
- Guidance-DataType
- Library-Extensions
- Profile-MedicationDispense
- Home-ContactUs

**Note**: The topic only needs to be added for pages that will be linked to directly, and for pages with non unique names, such as <code>Index</code> - for uniquely named pages e.g. <code>ValueSet England-[ValuesetName]</code>, the default generated topic is ok. 

---

## Structure Definition

The structure definition contains the profile’s description and profile purpose, rendered from the xml file using Firely Query Language (FQL). This contains a short description of the profiles purpose and the profile itself within a table. The profile table reference SHALL be rendered as below, ensuring that each view has the correct profile link. 

The tabs and rendered views SHALL be enclosed within a <code>\<nocheck></code> tag to allow for skipping of the spell checker due to the many spelling mistakes within the base HL7 render.

All examples relating to the profile, including those for extensions in the profile, SHALL be included within the Examples view. A profile SHALL have at least one example. 


~~~~html
# StructureDefinition-England-[profile]

<div id="transpose">
@ ```
from
	StructureDefinition
where
	name = 'England[profile name]'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>

@ ```
from
	StructureDefinition
where
	name = 'England[profile name]'
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
{ {tree:https://fhir.hl7.org.uk/StructureDefinition/England-[profile], snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{ {tree:https://fhir.hl7.org.uk/StructureDefinition/England-[profile], diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{ {tree:https://fhir.hl7.org.uk/StructureDefinition/England-[profile], hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{ {table:https://fhir.hl7.org.uk/StructureDefinition/England-[profile], snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:https://fhir.hl7.org.uk/StructureDefinition/England-[profile], snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:https://fhir.hl7.org.uk/StructureDefinition/England-[profile], snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>[profile]</b> - An example to illustrate the [reason for example].
<br>{ {pagelink:Example-England-[profile]}}
</div>
</nocheck>
~~~~

---

## Example Usage Scenarios

Any example use cases that are specific to the profile and relevant to NHS England can be added here. If there are no examples, then this section is not to be added to the page. If there are example, then it SHALL be in the following format: 

~~~html
### Example Usage Scenarios

The following are feasible use cases for the England [profile] profile:

- [usage scenario]. 

---
~~~

---

## Profile Specific Implementation Guidance
This contains any relevant information specifically to the profile. Within this page it may contain use cases or the minimum viable content. The title SHALL be added to the index page, but any information below is optional. 

~~~html
## Profile Specific Implementation Guidance: ##

[add any specific implementation or use case guidance]
~~~

---

## Minimum Viable Content

The minimum viable content (MVC) is any element in which has information that the provider and consumer systems SHOULD send or collect. Note, if mandatory data elements (e.g. 1..1 or 1..*) are present then these SHALL be included in the MVC.  

MVC SHALL be determined by use cases, and by analysis of the MustSupport flags used by other FHIR IG's, such as UK Core, US Core, Aus Base, Wales DHCW, NHSE IG, HL7 EU Lab.

~~~~html
<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>[element]</code></td>
<td>[reason].</td>
</tr>
</table>

---
~~~~

---

## Extensions

Any extension referenced within the profile SHALL be added to the Extensions page and  table, along with the element in which it is to be used and a link to the extension page within the IG.  

If no information on the use of any extensions is needed, then the page SHALL be in the following format: 

~~~~html
## Extensions

More information about the extensions can be found using the links below.

<table class="assets">
<tr>
<th width="20%">Extension</th>
<th width="20%">Context</th>
<th width="30%">Link</th>
<th width="30%">Comment</th>
</tr>
<tr>
<td>[extension name]</td>
<td>[context of use]</td>
<td>{ {pagelink:Extension-England-[extension]}}</td>
<td>[information on the use of the extension]</td>
</tr>
</table>

---
~~~~

---

## Bindings

Any coding / CodeableConcept element within the profile or within an extension within the profile, that is bound to a England ValueSet, SHALL be added to the Bindings (differential) page and table, via a listing of the element in which it is to be used, the binding strength and a link to the ValueSet page within the IG. 

~~~~html
## Bindings (differential)

More information about the bindings to NHS England ValueSets can be found below.

<table class="assets">
<tr>
<th width="30%">Context</th>
<th width="20%">Strength</th>
<th width="50%">Link</th>
</tr>
<tr>
<td>[context of use]</td>
<td>[strength]</td>
<td>{ {pagelink:ValueSet-England-[ValueSet]}}</td>
</tr>
</table>

---
~~~~

---

## Constraints

Any profile or profile element that has an additional constraint applied SHALL be added to the Constraints (differential) table, via a listing of the key, strength, expression and description of the constraint. 

~~~~html
## Constraints (differential)

More information about the constraints on the <code>England-[profile]</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>[constraint key]</td>
<td>[strength]</td>
<td>[fhirpath criteria to be valid]
</td>
<td>[human readable description of valid criteria].</td>
</tr>
</table>

---
~~~~

Elements in the expression SHALL be enclosed in <code>\<code></code> tags, e.g. 
~~~~html
<code>effective</code>.exists() or (<code>effective</code>.empty() and (<code>status</code> in ('partial' | 'preliminary' | 'final' | 'amended' | 'corrected' | 'appended')).not())
~~~~

Where the severity is a <samp>warning</samp>, the Human Description will say SHOULD, where the severity is <samp>error</samp>, it will say SHALL.

---