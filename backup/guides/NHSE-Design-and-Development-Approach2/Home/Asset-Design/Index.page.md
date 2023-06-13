## {{page-title}}


## FHIR Assets

This section documents the approach used by the IOPS to produce and maintain the NHS England Implementation Guides and the NHS England FHIR assets. It will be updated and matured in line with decisions taken during the Clinical and Technical Assurance process. This documentation is aimed at the technical reader and is included as reference material. The approach is based on the design principles.

## Conformance

The NHS England IG conforms to the HL7 FHIR® specification (Release 4) and its assets are profiles derived from the corresponding UK Core Profiles.

Further information about conformance in FHIR is available.

## Design Principle

### Key Principle:

FHIR assets shall be England specific and shall be capable of representing the requirements of NHS England. The assets shall only be created where there is a valid requirement to further constraint the UK Core assets or in the case of extensions to extend the UK Core. 

### Other Principles

#### Reference DataType

References in profiles shall use the FHIR base resource name only and there will be clear documentation on each profile page to explain how this relates to profiles (NHS England or UK Core).

Vendors shall build to UK Core profiles in data exchanges see the section on conformance in [NHS England IG](https://simplifier.net/guide/nhs-england-fhir-implementation-guide?version=current).

#### Extensions

There is a NHS England IG requirement to develop extensions based on any equivalent CareConnect STU3 extensions. The exception to this is where an extension is no longer needed because either:

- the data can be carried in a new element for a relevant resource in FHIR R4 
- a corresponding common extension has been developed in FHIR R4

Extension will be constrained (hard coded) into profiles to profiles after agreement during Clinical and Technical assurance.

The Implementation Guide for the NHS England IG will include an Extension Library page, which will list extensions and their corresponding NHS England IG profiles. There is no requirement to profile HL7 extensions locally. Where a HL7 extension is identified as in scope, a link to it will be added on the Extension Library page under HL7 Common Extensions.

Read more about [FHIR Extensions](https://www.hl7.org/fhir/r4/extensibility.html) and [Extension Design.](https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Asset-Design/Extension-Design?version=current)

#### Cardinalities
FHIR resource element cardinalities will only be amended, if clinical justifications are agreed during Clinical and Technical assurance.
No elements will be removed unless deemed clinically unsafe following consultation and agreement during Clinical and Technical assurance.
Read more about FHIR resource [cardinalities.](http://hl7.org/fhir/r4/profiling.html#cardinality)

#### Slicing
SHALL only be used where it enforces structure in a profile, for example
for a ValueSet binding
for the representation of an identifier in a list, such as a patient's NHS number
Slicing SHALL be Open e.g. one or more additional slices can be added.
Read more about [Slicing](https://www.hl7.org/fhir/r4/profiling.html#slicing) in FHIR.

#### Must Support
Will only be used when there is a requirement arising from a use case identified during Clinical and Technical assurance.
Read more about "Must Support" in FHIR.

#### ValueSets
Binding Strengths
The UKCore ValueSet binding strength SHOULD be decided as part of the Clinical and Technical Assurance, but the general philosophy is as the following:

- required - Used only when defined as 'required' by the FHIR standard, or when decided as part of the Clinical and Technical Assurance.
- extensible - All ValueSets SHOULD be set to 'extensible', where not defined as 'required' by the FHIR standard, or 'preferred' by the NHSE IG standard.
- preferred - Used when the ValueSet contains SNOMED CT or dm+d concepts due to their inherent complexities, or when decided as part of the Clinical and Technical Assurance.
- example - Decided as part of the Clinical and Technical Assurance.
Read more about [ValueSets](https://www.hl7.org/fhir/r4/terminologies.html#valuesets) and [ValueSet bindings](https://www.hl7.org/fhir/r4/terminologies.html#strength) in FHIR.

#### Validation
All FHIR assets SHALL be validated before being publicly available. See [Validation of Implementations](https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/ConformanceandDependencies/ValidationofImplementations.guide.md?version=current) for more details.

#### FHIR Resource Spelling
FHIR Resources, along with ValueSets, CodeSystems and ConceptMaps use the American-English spelling, for example Organization. The NHS England IG approach is to use American-English for any Profile, Extension, ValueSet, CodeSystem, and ConceptMap names, and when directly referring to the names within the Implementation Guide, otherwise using the British-English for all other aspects.


