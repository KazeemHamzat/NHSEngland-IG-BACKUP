## `requester`

| | |
|----|----|
|Element Id|ServiceRequest.requester|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([England PractitionerRoleMinimal](https://simplifier.net/nhs-england-implementation-guide/england-practitionerrole-duplicate-2))<br/> Aggregation - <a href="http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html" target="_blank">contained</a>|

<br/>

#### Definition

Who is created the Request or the Event. In NHSDigital API's this **SHOULD** always be a PractitionerRole role reference.


This will reference a `contained` PractitionerRole (note: this resource only contains limited user metadata such as ODS Code, professional code and SDS User Profile Id). This resource should not hold data which is held in SDS, only enough information to identify the SDS Entry.

**e-RS**

The contained PractitionerRole must contain

- SDS User ID of the Referrer in `practitioner`
- ODS Code of the Referring Organisation in `organization`

---