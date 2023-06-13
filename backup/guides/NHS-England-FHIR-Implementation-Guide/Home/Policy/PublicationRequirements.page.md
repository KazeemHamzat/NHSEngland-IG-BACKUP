### Publication Requirements

 <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Work in progress</div>

 
FHIR API definitions will be developed and version controlled in public Git repositories, held on Github. This is used for the day-to-day development of new specifications and changes to existing specifications. This includes both formal FHIR profile resources, and also API implementation guide content assets. Those wishing to contribute towards the development of the API specifications themselves should do so through Github (by raising issues, pull requests, etc.)

<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-PUB-01:</b>

<br/>
<br/>

- All FHIR resources and supporting assets held on Github.

<br/>
<br/>

The Github repository for NHS Digital is https://github.com/NHSDigital/NHSDigital-FHIR-ImplementationGuide

All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.) <b>MUST</b> be held on a publicly available GitHub repository which <b>MAY</b> be sychronised with a Simplifier project.
<p>Comments, feedback and suggestions from developers on FHIR resources (and associated documentation) <b>SHOULD</b> be managed through Simplifier using the standard features for raising and tracking issues on the site.</p>
<br/>
</div>
<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-PUB-02:</b>

<br/>
<br/>

- All FHIR resources published on a public FHIR Implementation Guide and released as an [FHIR Package](https://registry.fhir.org/learn).

<br/>
<br/>

All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.) that are ready for external use (in either DRAFT or ACTIVE status) <b>MAY</b> also be made available the NHS Digital FHIR reference server [fhir.nhs.uk](https://fhir.nhs.uk).
**Note:** Simplifier is now the development platform for all R4 FHIR Assets and therefore this requirement is currently under review within NHS Digital. 

Resources that are part of Care Connect (under the governance of INTEROPen) <b>MAY</b> also be published on a HL7 UK branded public FHIR server [fhir.hl7.org.uk](https://fhir.hl7.org.uk).
<br/><br/>
**Note:** CareConnect has been migrated to the Simplifier platform and therefore this requirement is currently under review with INTEROPen. 
</div>
<br/>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-PUB-03:</b>

<br/>
<br/>

- All FHIR resource URIs <b>Should</b> be resolvable URLs

<br/>
<br/>

<p>All FHIR resources relating to national systems and other nationally defined FHIR API profiles (including StructureDefinitions, ValueSets, OperationDefinitions, ImplementationGuides, etc.) <b>SHOULD</b> have a URI that is a resolvable URL. Usually this will be the URL of the resource on the FHIR API reference server <code>https://fhir.nhs.uk</code> or <code>https://fhir.hl7.org.uk</code></p>
This is currently not possible however there is discussion ongoing about development   
</div>
<br/>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-PUB-04:</b>

<br/>
<br/>

- FHIR API Maturity.

<br/>
<br/>
	
When any FHIR implementation guides are published, they <b>MUST</b> have an associated maturity label. These <b>SHOULD</b> be the labels used by the GDS development process stages, and will be one of:

- **Discovery**: a Feasibility study. A 'No code' development. Designed to find out what users are trying to achieve, any constraints, improvement opportunities
- **Alpha**: Develop prototypes and test with users. Could be minimal functionality and potentially prototypes for any options to determine which is best
- **Private Beta**: Working version and test with invited users. Handle real transactions and work at scale. ‘Invite only’ or regional. Must Pass assessment by business and technical SME’s
- **Public Beta**: All users can participate. Version unlikely to change substantially, but still needs further testing by a wider group of implementors before becoming live
- **Live**: The live phase is about supporting the service in a sustainable way, and continuing to iterate and make improvements
- **Retiring**: Implementors notified that the service is discontinued and not to be used for new developments
<br/>
#### Previously the NHS Digital process stages were defined as: (<b>MUST NOT</b> be used for any R4 FHIR development)
 - **Experimental**: Early development/proof of concept version of an API for early sight during discovery.
 - **Alpha**: Initial test APIs, likely to change substantially.
	- Typical Usage: Engagement with others interested in being involved with early development work and influencing the direction taken.
 - **Beta**: APIs that are still under active development and subject to change
	- Typical Usage: Engagement with 'first of type' or early adopters by the creation of first of type or pilot systems for testing, proof of concept etc. This development can assist in progression to a release candidate for a wider rollout.
 - **Release Candidate**: APIs that are largely complete, unlikely to change substantially, but still need further testing by a wider group of implementers before becoming live.
	- Typical Usage: After having been previously implemented by 'first of type' or pilot sites and now to be rolled out to a wider group of implementers.
 - **Live**: Release live APIs
 - **Discontinued**: APIs which have been discontinued and should not be used for new development
 
#### The GDS and previous process stages map as follows:
 
 |GDS          |NHS Digital (previous)|
 |-------------|----------------------|
 |Discovery    |Experimental          |
 |Alpha        |Alpha                 |
 |Private Beta |Beta                  |
 |Public Beta  |Release Candidate     |
 |Live         |Live                  |
 |Retiring     |Discontinued          | 

</div>