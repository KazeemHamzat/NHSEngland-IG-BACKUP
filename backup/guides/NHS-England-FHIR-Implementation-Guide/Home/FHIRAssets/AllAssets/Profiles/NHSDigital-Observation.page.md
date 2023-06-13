### NHSDigital-Observation

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Observation](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Observation}) | {{pagelink:Diagnostics}} | trial-use |

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
         <br/>
         Combined with
          <br/>
        {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Observation, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
         <br/>
  from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation}} 
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Observation, diff}}
        </div>
           <div id="Constraints"  class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Observation'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples"  class="tab-pane">
<br />
- {{pagelink:SARS-CoV-2-ORGY}}

</div>
</div>

### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Observation' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
```

---

<br/>

 #### Definition

 Measurements and simple assertions made about a patient, device or other subject.

 #### Comment

 Used for simple observations such as device measurements, laboratory atomic results, vital signs, height, weight, smoking status, comments, etc.  Other resources are used to provide context for observations such as laboratory reports, etc.

 #### Constraints 

- **obs-6** (*ERROR*) dataAbsentReason SHALL only be present if Observation.value[x] is not present
- **obs-7** (*ERROR*) If Observation.code is the same as an Observation.component.code then the value element associated with the code SHALL NOT be present


- <a href="#extension:covid19Testing">extension:covid19Testing</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#category">category</a>
- <a href="#category.coding.system">category.coding.system</a>
- <a href="#category.coding.code">category.coding.code</a>
- <a href="#category:COVID-TestPillar">category:COVID-TestPillar</a>
- <a href="#category:COVID-TestPillar.coding.system">category:COVID-TestPillar.coding.system</a>
- <a href="#category:UKCoreCategory">category:UKCoreCategory</a>
- <a href="#category:UKCoreCategory.coding.system">category:UKCoreCategory.coding.system</a>
- <a href="#code">code</a>
- <a href="#code.coding:snomedCT">code.coding:snomedCT</a>
- <a href="#code.coding:snomedCT.system">code.coding:snomedCT.system</a>
- <a href="#code.coding:loinc">code.coding:loinc</a>
- <a href="#code.coding:loinc.system">code.coding:loinc.system</a>
- <a href="#subject">subject</a>
- <a href="#subject.identifier.system">subject.identifier.system</a>
- <a href="#effective[x]">effective[x]</a>
- <a href="#performer">performer</a>
- <a href="#value[x]">value[x]</a>
- <a href="#bodySite.coding:snomedCT">bodySite.coding:snomedCT</a>
- <a href="#bodySite.coding:snomedCT.system">bodySite.coding:snomedCT.system</a>
- <a href="#method">method</a>
- <a href="#specimen">specimen</a>
- <a href="#device">device</a>
- <a href="#component.code.coding:snomedCT">component.code.coding:snomedCT</a>
- <a href="#component.code.coding:snomedCT.system">component.code.coding:snomedCT.system</a>

<a name="extension:covid19Testing"></a>
 ## extension:covid19Testing

| | |
|----|----|
|Element Id|Observation.extension:covid19Testing|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|covid19Testing|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionCOVID19TestResult](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-COVID19-TestResult))|

<br/>

 #### Definition

 Optional Extension Element - found in all resources.

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Observation.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 A unique identifier assigned to this observation.

For COVID-19 Test History this will be The identifier will be the specimen id.

```json

    "identifier":  [
        {
            "system": "https://fhir.nhs.uk/Id/SpecimenId",
            "value": "eb89a392-5b20-11eb-ae93-0242ac130002"
        }
    ],
```

 #### Requirements

 Allows observations to be distinguished and referenced.

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|Observation.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ObservationStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/observation-status&#124;4.0.1) (Required) <br/>Codes providing the status of an observation. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 The status of the result value.

For COVID-19 Test History the status of the observation will always be `final`

```json

    "status": "final",
```

 #### Requirements

 Need to track the status of individual results. Some results are finalised before the whole report is finalised.

 #### Comment

 This element is labelled as a modifier because the status contains codes that mark the resource as not currently valid.

<a name="category"></a>
 ## category

| | |
|----|----|
|Element Id|Observation.category|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ObservationCategory](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-Observation-category) (Required)|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *coding.system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 This is an optional element. If used the category will always be `laboratory`

```json

    "category":  [
        {
            "coding":  [
                {
                    "system": "http://terminology.hl7.org/CodeSystem/observation-category",
                    "code": "laboratory",
                    "display": "Laboratory"
                }
            ],
            "text": "Laboratory"
        }
    ],
```

For COVID-19 Tests, the ValueSet **SHOULD** be used to indicate which test pillar the observation originated.

```json

     "category": [
        {
            "coding": [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/covid-test-pillar",
                    "code": "pillar-1",
                    "display": "pillar 1"
                }
            ]
        }
    ],
```

 #### Requirements

 Used for filtering what observations are retrieved and displayed.

 #### Comment

 In addition to the required category valueset, this element allows various categorization schemes based on the owner’s definition of the category and effectively multiple categories can be used at once.  The level of granularity is defined by the category concepts in the value set.

<a name="category.coding.system"></a>
 ## category.coding.system

| | |
|----|----|
|Element Id|Observation.category.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="category.coding.code"></a>
 ## category.coding.code

| | |
|----|----|
|Element Id|Observation.category.coding.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 A symbol in syntax defined by the system. The symbol may be a predefined code or an expression in a syntax defined by the coding system (e.g. post-coordination).

 #### Requirements

 Need to refer to a particular code in the system.

<a name="category:COVID-TestPillar"></a>
 ## category:COVID-TestPillar

| | |
|----|----|
|Element Id|Observation.category:COVID-TestPillar|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ObservationCategoryCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/observation-category) (Preferred) <br/>Codes for high level observation categories. |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|COVID-TestPillar|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 A code that classifies the general type of observation being made.

 #### Requirements

 Used for filtering what observations are retrieved and displayed.

 #### Comment

 In addition to the required category valueset, this element allows various categorization schemes based on the owner’s definition of the category and effectively multiple categories can be used at once.  The level of granularity is defined by the category concepts in the value set.

<a name="category:COVID-TestPillar.coding.system"></a>
 ## category:COVID-TestPillar.coding.system

| | |
|----|----|
|Element Id|Observation.category:COVID-TestPillar.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/covid-test-pillar|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="category:UKCoreCategory"></a>
 ## category:UKCoreCategory

| | |
|----|----|
|Element Id|Observation.category:UKCoreCategory|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ObservationCategoryCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/observation-category) (Preferred) <br/>Codes for high level observation categories. |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|UKCoreCategory|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 A code that classifies the general type of observation being made.

 #### Requirements

 Used for filtering what observations are retrieved and displayed.

 #### Comment

 In addition to the required category valueset, this element allows various categorization schemes based on the owner’s definition of the category and effectively multiple categories can be used at once.  The level of granularity is defined by the category concepts in the value set.

<a name="category:UKCoreCategory.coding.system"></a>
 ## category:UKCoreCategory.coding.system

| | |
|----|----|
|Element Id|Observation.category:UKCoreCategory.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|http://terminology.hl7.org/CodeSystem/observation-category|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="code"></a>
 ## code

| | |
|----|----|
|Element Id|Observation.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[LOINCCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/observation-codes) (Example) <br/>Codes identifying names of simple observations. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Type of observation, for COVID-10 see [Observation Definition](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/ObservationDefinition/ObservationDefinition.guide.md) for `code` values.

```json
    "code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "871555000",
                "display": "Detection of ribonucleic acid of Severe acute respiratory syndrome coronavirus 2"
            }
        ]
    },
```

 #### Requirements

 Knowing what kind of observation is being made is essential to understanding the observation.

 #### Comment

 *All* code-value and, if present, component.code-component.value pairs need to be taken into account to correctly understand the meaning of the observation.

<a name="code.coding:snomedCT"></a>
 ## code.coding:snomedCT

| | |
|----|----|
|Element Id|Observation.code.coding:snomedCT|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[UKCoreObservationType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-ObservationType) (Extensible) <br/>A code from the SNOMED Clinical Terminology UK coding system describing a type of observation |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|snomedCT|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="code.coding:snomedCT.system"></a>
 ## code.coding:snomedCT.system

| | |
|----|----|
|Element Id|Observation.code.coding:snomedCT.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://snomed.info/sct|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="code.coding:loinc"></a>
 ## code.coding:loinc

| | |
|----|----|
|Element Id|Observation.code.coding:loinc|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|loinc|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="code.coding:loinc.system"></a>
 ## code.coding:loinc.system

| | |
|----|----|
|Element Id|Observation.code.coding:loinc.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://loinc.org|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="subject"></a>
 ## subject

| | |
|----|----|
|Element Id|Observation.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Group](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Group) [Device](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Device) [UKCoreLocation](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location) [NHSDigitalPatientMinimal](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient-Minimal))|

<br/>

 #### Definition

 The NHS Number will be an identifier reference which can be used with PDS FHIR API to return Patient demographics. If a local Patient is available, a reference to this will be present (e.g. "Patient/123")

```json

    "subject": {
        "reference": "Patient/123",
        "identifier":  [
            {
                "system": "https://fhir.nhs.uk/Id/nhs-number",
                "value": "987123456"
            }
        ]
    },
```

 #### Requirements

 Observations have no value if you don't know who or what they're about.

 #### Comment

 One would expect this element to be a cardinality of 1..1. The only circumstance in which the subject can be missing is when the observation is made by a device that does not know the patient. In this case, the observation SHALL be matched to a patient through some context/channel matching technique, and at this point, the observation should be updated.

 #### Constraints 

- **patient-reference** (*WARNING*) subject - An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="subject.identifier.system"></a>
 ## subject.identifier.system

| | |
|----|----|
|Element Id|Observation.subject.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/nhs-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="effective[x]"></a>
 ## effective[x]

| | |
|----|----|
|Element Id|Observation.effective[x]|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 The date and time the result was asserted.

```json

    "effectiveDateTime": "2020-09-23T13:00:08.476+00:00"
```

 #### Requirements

 Knowing when an observation was deemed true is important to its relevance as well as determining trends.

 #### Comment

 At least a date should be present unless this observation is a historical report.  For recording imprecise or "fuzzy" times (For example, a blood glucose measurement taken "after breakfast") use the [Timing](http://hl7.org/fhir/R4/datatypes.html#timing) datatype which allow the measurement to be tied to regular life events.

<a name="performer"></a>
 ## performer

| | |
|----|----|
|Element Id|Observation.performer|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization) [CareTeam](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/CareTeam) [NHSDigitalPatient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient) [NHSDigitalPractitionerRoleMinimal](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-Minimal)[NHSDigitalReference](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Reference))|

<br/>

 #### Definition

 Who was responsible for asserting the observed value as "true". 

```json

"performer": [
  {
    "type": "Organization",
    "identifier": {
      "type": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/CodeSystem/organisation-role",
            "code": "173",
            "display": "PATHOLOGY LAB"
          }
        ]
      },
      "value": "LFD004"
    }
  },
  {
    "type": "Organization",
    "identifier": {
      "type": {
        "coding": [
          {
            "system": "https://fhir.nhs.uk/Id/OrgType",
            "code": "TestCentreId",
            "display": "Testing Centre"
          }
        ]
      },
      "value": "WKE03"
    }
  }
]

```

 #### Requirements

 May give a degree of confidence in the observation and also indicates where follow-up questions should be directed.

 #### Comment

 References SHALL be a reference to an actual FHIR resource, and SHALL be resolvable (allowing for access control, temporary unavailability, etc.). Resolution can be either by retrieval from the URL, or, where applicable by resource type, by treating an absolute reference as a canonical URL and looking it up in a local registry/repository.

 #### Constraints 

- **performer** (*ERROR*) An identifier reference or resource reference must be provided

<a name="value[x]"></a>
 ## value[x]

| | |
|----|----|
|Element Id|Observation.value[x]|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Quantity](https://www.hl7.org/fhir/datatypes.html#Quantity)[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)[string](https://www.hl7.org/fhir/datatypes.html#string)[boolean](https://www.hl7.org/fhir/datatypes.html#boolean)[integer](https://www.hl7.org/fhir/datatypes.html#integer)[Range](https://www.hl7.org/fhir/datatypes.html#Range)[Ratio](https://www.hl7.org/fhir/datatypes.html#Ratio)[SampledData](https://www.hl7.org/fhir/datatypes.html#SampledData)[time](https://www.hl7.org/fhir/datatypes.html#time)[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)[Period](https://www.hl7.org/fhir/datatypes.html#Period)|

<br/>

 #### Definition

 ### COVID-19 valueCodeableConcept 

The COVID 19 test result. This is a SNOMED CT from the valueSet associated with the `code`, see [Observation Definition](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/ObservationDefinition/ObservationDefinition.guide.md)

```json 

    "valueCodeableConcept": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "1240581000000104",
                "display": "SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) detection result positive"
            }
        ],
        "text": "SARS-CoV-2-ORGY"
    },
```

 #### Requirements

 An observation exists to have a value, though it might not if it is in error, or if it represents a group of observations.

 #### Comment

 An observation may have; 1)  a single value here, 2)  both a value and a set of related or component values,  or 3)  only a set of related or component values. If a value is present, the datatype for this element should be determined by Observation.code.  A CodeableConcept with just a text would be used instead of a string if the field was usually coded, or if the type associated with the Observation.code defines a coded value.  For additional guidance, see the [Notes section](http://hl7.org/fhir/R4/observation.html#notes) below.

<a name="bodySite.coding:snomedCT"></a>
 ## bodySite.coding:snomedCT

| | |
|----|----|
|Element Id|Observation.bodySite.coding:snomedCT|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[UKCoreBodySite](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-BodySite) (Extensible) <br/>A code from the SNOMED Clinical Terminology UK with the expression (<<442083009 |anatomical or acquired body structure|) |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|snomedCT|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="bodySite.coding:snomedCT.system"></a>
 ## bodySite.coding:snomedCT.system

| | |
|----|----|
|Element Id|Observation.bodySite.coding:snomedCT.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://snomed.info/sct|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="method"></a>
 ## method

| | |
|----|----|
|Element Id|Observation.method|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ObservationMethods](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/observation-methods) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 The name of the test that was performed, this is a SNOMED CT concept.

```json

    "method": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "1240461000000109",
                "display": "Measurement of SARS-CoV-2 antibody (procedure)"
            }
        ]
    },
```

 #### Requirements

 In some cases, method can impact results and is thus used for determining whether results can be compared or determining significance of results.

 #### Comment

 Only used if not implicit in code for Observation.code.

<a name="specimen"></a>
 ## specimen

| | |
|----|----|
|Element Id|Observation.specimen|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Specimen](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Specimen))|

<br/>

 #### Definition

 For COVID-19 Test History. The identifier of the specimen used for the test.
 
```json

    "specimen": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/SpecimenId",
            "value": "eb89a392-5b20-11eb-ae93-0242ac130002"
        }
    },
```

 #### Comment

 Should only be used if not implicit in code found in `Observation.code`.  Observations are not made on specimens themselves; they are made on a subject, but in many cases by the means of a specimen. Note that although specimens are often involved, they are not always tracked and reported explicitly. Also note that observation resources may be used in contexts that track the specimen explicitly (e.g. Diagnostic Report).

<a name="device"></a>
 ## device

| | |
|----|----|
|Element Id|Observation.device|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Device](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Device) [DeviceMetric](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/DeviceMetric))|

<br/>

 #### Definition

 Details of the [COVID-19 test kit](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/Id/Covid19-TestKit) used.  

```json

    "device": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/Covid19-TestKit",
            "value": "LFT"
        },
        "display": "Lateral Flow Test"
    }
```

 #### Comment

 Note that this is not meant to represent a device involved in the transmission of the result, e.g., a gateway.  Such devices may be documented using the Provenance resource where relevant.

<a name="component.code.coding:snomedCT"></a>
 ## component.code.coding:snomedCT

| | |
|----|----|
|Element Id|Observation.component.code.coding:snomedCT|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[UKCoreObservationType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-ObservationType) (Extensible) <br/>A code from the SNOMED Clinical Terminology UK coding system describing a type of observation |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|snomedCT|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labelled as UserSelected = true.

<a name="component.code.coding:snomedCT.system"></a>
 ## component.code.coding:snomedCT.system

| | |
|----|----|
|Element Id|Observation.component.code.coding:snomedCT.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://snomed.info/sct|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.