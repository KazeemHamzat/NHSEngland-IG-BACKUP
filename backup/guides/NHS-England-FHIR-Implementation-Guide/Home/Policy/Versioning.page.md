### Versioning

 <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Work in progress</div>
 
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-VER-01:</b>

<br/>
<br/>

- Versioning of Profiles and Resources

<br/>
<br/>

Nationally defined FHIR profiles will be versioned during development using Git, and this will follow the standard GitFlow model.
The versioning for published artefacts will broadly follow [semantic versioning standards](http://semver.org/)

The major and minor versions will be visible, and the patch version <b>MAY</b> also be exposed.

Version numbers held in profiles and resource instances <b>MUST</b> therefore be in one of the following forms:

- MAJOR – e.g. 1
- MAJOR.MINOR – e.g. 1.0
- MAJOR.MINOR.PATCH – e.g. 1.0.2"

Definitions:

- Minor Change
   - A minor change is defined as a backwards-compatible change which is not expected to break existing implementations. Examples include:
      - Addition of new optional fields in a profile
      - Addition of new operations whose name does not clash with existing operations
- Major Change
   - This is a breaking change, and as such, implementers will need to understand the changes that have been made in the new version, and make changes to their implementations if required.
- Resources
   - The versioning requirements relate to all resources served up from FHIR compliant endpoints. This include FHIR “profile” resources published nationally – including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, Conformance Statements, etc.
</div>
<br/>


<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> 
FHIR-VER-02:</b>

<br/>
<br/>

- HL7 FHIR version in FHIR Endpoint URL

<br/>
<br/>

Nationally delivered FHIR endpoints (i.e. servers that implement FHIR standards to serve FHIR resources or respond to calls to FHIR operations), including FHIR messaging endoints, <b>MUST</b> differentiate the HL7 FHIR version (e.g. DSTU2, STU3, etc) in the FHIR base URL.

This <b>MUST</b> follow the format: **https://[baseurl]/FHIR/[fhir-version]**

Where **[fhir-version]** is the uppercase alphanumeric major version name of the FHIR version in use (e.g. STU3 or R4) – see [this page](http://hl7.org/fhir/directory.html) for published versions.


NOTES:

- This also applies to the public FHIR API reference servers, which will publish profiles on URLs which follow this convention.
- The baseurl part may be just an FQDN, but may also have other path elements if required to uniquely identify the endpoints (e.g. where a system services requests relating to multiple organisations, an organisation code may form part of the baseurl).
</div>
<br/>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-VER-03:</b></br>

<br/>
<br/>

- Versioning of FHIR endpoint implementations

<br/>
<br/>

In addition to the HL7 FHIR version used, and the versioning of nationally published profiles, systems implementing those profiles in actual system endpoints will also want to be able to version those endpoints as they release new functionality or make changes to the resources they support in their endpoint.
This endpoint version will also be conveyed in the URL, and <b>MUST</b> follow the FHIR version in the URL path. The format of the version identifier will be defined by the implementer and could be in any URL-valid format. The combined structure of the URL will therefore be:

**https://[baseurl]/FHIR/[fhir-version]/[endpoint-version]**

NOTE: Some FHIR endpoint implementations may choose to be 'versionless' – i.e. they will always maintain full backwards compatibility between releases. In these cases the endpoint version can be omitted. An example of this is the FHIR API Reference Servers used to publish national profiles. These reference servers require stable and reliable URLs for profiles, so will not include an endpoint version in the URL.
</div>
<br/>
