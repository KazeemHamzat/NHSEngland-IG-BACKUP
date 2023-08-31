### Overview
This section details the version management approach used with the NHS England Implementation Guides, NHS England Implementation Guides packages and FHIR assets. The approach differs for each of these items and so is documented in separate sections.

### FHIR Assets Versioning
All profiles produced for the NHSE IG will be versioned during development using <a href="https://git-scm.com/" Target="_blank"> Git</a> and will follow the standard <a href="https://guides.github.com/introduction/flow/" Target="_blank"> GitFlow model</a>.   

The version information is maintained by the IOPS team in line with the Semantic Versioning Standard outlined above. Thus, for a StructureDefinition, this could read:

````xml
<StructureDefinition xmlns="http://hl7.org/fhir">
  <id value="England-Patient" />
  <url value="https://fhir.nhs.uk/StructureDefinition/England-Patient" />
  <version value="2.1.0" />
````
For a ValueSet, this could read:

````xml
<ValueSet xmlns="http://hl7.org/fhir">
<id value="England-MedicationForm"/>
<url value="https://fhir.nhs.uk/ValueSet/England-MedicationForm"/>
<version value="2.0.0"/>
````


<code>https://fhir.nhs.uk/StructureDefinition/England-RelatedPerson|1.1.0</code>

This is illustrated below:

````xml
<RelatedPerson xmlns="http://hl7.org/fhir">
    <id value="RP123" />
    <meta>
        <profile value="https://fhir.nhs.uk/StructureDefinition/England-RelatedPerson|1.1.0" />
    </meta>
````

### Definitions of Change Types
There is no real way to determine whether a NHS England IG change is breaking or not unless you can get agreement with every implementer of the NHS England IG. This is practically impossible to do, so the following sections are to give a brief overview of the sort of changes that might be seen as breaking changes and should not be seen as definitive. 
#### Major Change
This is a breaking change, and as such, implementers will need to understand the changes that have been made in the new version, and make changes to their implementations, if required, as such a change is not backwards compatible. An example could be :-
-  Addition of new mandatory element(s) in a profile
#### Minor Change
A minor change is defined as a backwards compatible change which is not expected to break existing implementations. Examples include :-
-  Addition of new optional element(s) in a profile
-  Addition of new operations whose names do not clash with existing operations
#### Patch
This is defined as a version in which backwards compatible bug fixes are made. An example could be :-
-  Correcting typos in the short description of an element in a FHIR profile

The NHS England IG is released as a pre-release for comment before an actual release, this will be with full change history for the changes applied so that implementers can agree the versioning that has been applied to the FHIR assets.

## Semantic Versioning

Given a version number MAJOR.MINOR.PATCH, increment the:

MAJOR version when you make incompatible changes, MINOR version when you add functionality in a backwards-compatible manner, and PATCH version when you make backwards-compatible bug fixes. Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

## Pre-Release Labels
These labels will be taken from the GDS development process stages, and will be one of:

- **Discovery**: a Feasibility study. A 'No code' development. Designed to find out what users are trying to achieve, any constraints, improvement opportunities

- **Alpha**: Develop prototypes and test with users. Could be minimal functionality and potentially prototypes for any options to determine which is best

- **Private Beta**: Working version and test with invited users. Handle real transactions and work at scale. ‘Invite only’ or regional. Must Pass assessment by business and technical SME’s

- **Public Beta**: All users can participate. Version unlikely to change substantially, but still needs further testing by a wider group of implementors before becoming live

- **Live**: The live phase is about supporting the service in a sustainable way, and continuing to iterate and make improvements

- **Retiring**: Implementors notified that the service is discontinued and not to be used for new developments

### Publication of a version within a NHSE IG asset
Version data will be carried in the version element for all assets.   
These assets are :-
- <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide/Home/ProfilesandExtensions/ProfilesIndex.page.md?version=current" Target="_blank"> StructureDefinitions</a> 
-  <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide/Home/ProfilesandExtensions/ExtensionLibrary" Target="_blank"> Extensions</a>
- <a href="https://simplifier.net/guide/uk-core-implementation-guide/Home/Terminology/ValueSetsandCodeSystems" Target="_blank"> ValueSets/CodeSystems</a>
- <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide/Home/Terminology/ConceptMaps" Target="_blank"> ConceptMaps</a>   

The version information is maintained by the <a href="https://simplifier.net/HL7FHIRUKCoreR4/~team" Target="_blank"> UK Core Development team</a> in line with the Semantic Versioning Standard outlined above. Thus, for a StructureDefinition, this could read:

````xml
<StructureDefinition xmlns="http://hl7.org/fhir">
  <id value="UKCore-Patient" />
  <url value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient" />
  <version value="2.1.0" />
````   
For a ValueSet, this could read:

````xml
<ValueSet xmlns="http://hl7.org/fhir">
<id value="UKCore-MedicationForm"/>
<url value="https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationForm"/>
<version value="2.0.0"/>
````
Further information about both FHIR asset creation and maintenance is available on the [Asset Design](https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home/Asset-Design?version=current "Title") page. 

### Instance Conformance Identification
For some information flows, there is a requirement to identify which NHSE IG profile(s) an instance being exchanged between healthcare IT systems conforms to. This could be for the purpose of validation of the instance against the profile definition and/or for conformance testing. This profile conformance is declared using the profile.meta element. The element carries the profile URL appended with the version information. 

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Most implementations will use NPM Packages for validation and therefore the use of this approach is not mandated when using NHSE IG profiles.   </div>

More information about NPM packages is available on the
[package versioning page.](https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home/Management/Version-Management?version=current#Package-Versioning)

The format is: 'URL' "\|" 'version'
For example:

<code>https://fhir.nhs.uk/R4/StructureDefinition/UKCore-RelatedPerson|1.1.0</code>

This is illustrated below:

````xml
<RelatedPerson xmlns="http://hl7.org/fhir">
    <id value="RP123" />
    <meta>
        <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson|1.1.0" />
    </meta>
````
---
