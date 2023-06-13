## NHSDigital-Organization

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization) | {{pagelink:Administration}} | normative |

<br>

### Conformance Rules

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
{{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization}} <br><br> 
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
  from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization, diff}}
        </div>
           <div id="Constraints"  class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples"  class="tab-pane">
<br />

- {{pagelink: Leedsteachingtrust}}
- {{pagelink: TheSwanMedicalCentre}}
- {{pagelink: leedsccg}}
- {{pagelink: NHSNightingaleHospitalYorkshireandtheHumber}}
- {{pagelink:HMP-Leeds}}


</div>
</div>

### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization'
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
```

<br/>

 #### Definition

 A formally or informally recognized grouping of people or organizations formed for the purpose of achieving some form of collective action.  Includes companies, institutions, corporations, departments, community groups, healthcare practice groups, payer/insurer, etc.

 #### Constraints 

- **org-1** (*ERROR*) The organization SHALL at least have a name or an identifier, and possibly more than one

<br/>

- <a href="#extension:organizationPeriod.url">extension:organizationPeriod.url</a>
- <a href="#identifier">identifier</a>
- <a href="#identifier:odsOrganisationCode">identifier:odsOrganisationCode</a>
- <a href="#identifier:odsOrganisationCode.system">identifier:odsOrganisationCode.system</a>
- <a href="#identifier:odsSiteCode">identifier:odsSiteCode</a>
- <a href="#identifier:odsSiteCode.system">identifier:odsSiteCode.system</a>
- <a href="#type.coding.system">type.coding.system</a>
- <a href="#name">name</a>
- <a href="#telecom">telecom</a>

<a name="extension:organizationPeriod.url"></a>
 ## extension:organizationPeriod.url

| | |
|----|----|
|Element Id|Organization.extension:organizationPeriod.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://hl7.org/fhir/StructureDefinition/organization-period|
|[type](https://www.hl7.org/fhir/datatypes.html)|[http://hl7.org/fhirpath/System.String](https://www.hl7.org/fhir/datatypes.html#http://hl7.org/fhirpath/System.String)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Organization.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 **MUST** contain an ANANA/ODS code. 

```json
 "identifier":  [
        {
            "use": "official",
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RR805"
        }
    ],
```

 #### Requirements

 Organizations are known by a variety of ids. Some institutions maintain several, and most collect identifiers for exchange with other organizations concerning the organization.

 #### Comment

 MUST contain an ANANA/ODS code.

<a name="identifier:odsOrganisationCode"></a>
 ## identifier:odsOrganisationCode

| | |
|----|----|
|Element Id|Organization.identifier:odsOrganisationCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|odsOrganisationCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 Identifier code supplier by the Organisation Data Service.

 #### Requirements

 Organizations are known by a variety of ids. Some institutions maintain several, and most collect identifiers for exchange with other organizations concerning the organization.

<a name="identifier:odsOrganisationCode.system"></a>
 ## identifier:odsOrganisationCode.system

| | |
|----|----|
|Element Id|Organization.identifier:odsOrganisationCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/ods-organization-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:odsSiteCode"></a>
 ## identifier:odsSiteCode

| | |
|----|----|
|Element Id|Organization.identifier:odsSiteCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..0|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|odsSiteCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 ODS Site code to identify the organisation at site level.

 #### Requirements

 Organizations are known by a variety of ids. Some institutions maintain several, and most collect identifiers for exchange with other organizations concerning the organization.

<a name="identifier:odsSiteCode.system"></a>
 ## identifier:odsSiteCode.system

| | |
|----|----|
|Element Id|Organization.identifier:odsSiteCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/ods-site-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="type.coding.system"></a>
 ## type.coding.system

| | |
|----|----|
|Element Id|Organization.type.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/organisation-role|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="name"></a>
 ## name

| | |
|----|----|
|Element Id|Organization.name|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 The ODS/SDS name of the Organisation

```json

    "name": "NHS NIGHTINGALE HOSPITAL YORKSHIRE AND THE HUMBER"
```

 #### Requirements

 Need to use the name as the label of the organization.

 #### Comment

 If the name of an organization changes, consider putting the old name in the alias column so that it can still be located through searches.

<a name="telecom"></a>
 ## telecom

| | |
|----|----|
|Element Id|Organization.telecom|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[ContactPoint](https://www.hl7.org/fhir/datatypes.html#ContactPoint)|

<br/>

 #### Definition

 Contact phone numbers and address of the organisation.

```json

    "telecom":  [
        {
            "system": "fax",
            "value": "0113 242 6496",
            "use": "work"
        },
        {
            "system": "phone",
            "value": "0113 243 3144",
            "use": "work"
        }
    ],
    "address":  [
        {
            "line":  [
                "KINGS ROAD"
            ],
            "city": "HARROGATE",
            "postalCode": "HG1 5LA",
            "country": "ENGLAND"
        }
    ],
    "partOf": {
        "reference": "https://directory.spineservices.nhs.uk/R4/Organization/RR805",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RR8"
        }
    }
```

 #### Requirements

 Human contact for the organization.

 #### Comment

 The use code 'home' is not to be used. Note that these contacts are not the contact details of people who are employed by or represent the organization, but official contacts for the organization itself.

 #### Constraints 

- **org-3** (*ERROR*) The telecom of an organization can never be of use 'home'