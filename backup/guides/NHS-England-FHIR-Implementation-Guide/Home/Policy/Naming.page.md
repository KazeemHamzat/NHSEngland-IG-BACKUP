### Naming

 <div markdown="span" class="alert alert-warning" role="alert">
 <i class="fas fa-exclamation-triangle"></i><b> Important:</b> Work in progress</div>

In order to promote consistency and make it easier for implementers to locate suitable profiles, extensions, value sets, etc, for their projects, a naming strategy will be adopted for UK Core defined FHIR assets or FHIR assets derived from the UK Core. All UK Core derived implementation guides and FHIR assets **MUST** follow these rules to claim conformance with the UK Core.

For detailed definitions of concepts discussed within this guidance document, refer to the appropriate published version of the [FHIR standard](https://www.hl7.org/fhir/).

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> FHIR-NHSDIGITAL-NAME-01: (Scope NHS Digital Profiles only)</b>

<br/>
<br/>

- FHIR Profile name <b>MUST</b> follow an agreed format.

<br/>
<br/>

This section details a set of rules that <b>MUST</b> be followed when creating NHS Digital FHIR profiles. The name of a profile consists of a number of name segments, and will be in the form:-

**[Base][Specialism][FHIRAssetName]**

The segments are defined as follows:-

- **Base**: The base profile this will always be NHSDigital <b>Mandatory</b>
- **Specialism**: <b>Required</b> - This is only used where there are multiple NHS Digital profiles for a given base resource type.
- **FHIRAssetName**: The name of the base FHIR Resource. <b>Mandatory</b>

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> Important  Note:</b>

<br/>
<br/>

Unlike CareConnect STU3, no version information is allowed in the R4 profile Name
<br/>
<br/>
This name <b>MUST</b> be used in three places:
- The profile's **filename**.
- The **name** of the profile - specifically the <code>name.value</code> element in the StructureDefinition
- The profile's **logical id**. This is carried in the element <code>StructureDefinition.id.value</code>

**Example of the name Usage**

```xml
    <StructureDefinition xmlns="http://hl7.org/fhir">
    <id value="NHSDigital-MedicationStatement" />
    <url value="https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationStatement" />
    <version value="1.0.0" />
    <name value="NHSDigitalMedicationStatement" />
```
</div>
</div>
<br/>

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> FHIR-NHSDIGITAL-NAME-02: (Scope NHSDigital Derived profiles only)</b>

<br/>
<br/>

- FHIR Profile name <b>MUST</b> follow an agreed format.

<br/>
<br/>

This section details a set of rules that <b>MUST</b> be followed when creating profiles derived from NHS Digital profiles to enable the profiles to claim conformance to NHS Digital. The name of a profile consists of a number of name segments, and will be in the form:-

**[BusinessName1] [BusinessName2] [FHIRAssetName]**

The segments are defined as follows:-

- **BusinessName1**: The first business name of the profile, which could be a full name or an acronym related to the domain or project name e.g. Digital Medication. The name <b>MUST</b> have at least one BusinessName segment for a derived profile. Where an asset may be used across several domains, business names <b>SHOULD</b> reflect that.
- **BusinessName2**: The second business name of the profile. The asset name <b>MAY</b> have a second BusinessName segment. 
- **FHIRAssetName**: The name of the base FHIR Resource. <b>Mandatory</b>

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i>

<br/>
<br/>

Important Notes:</b> <ol>
<li>Unlike CareConnect STU3, no version information is allowed in the R4 profile Name</li>
<li>The Profile name <b>MUST NOT </b>have UK Core in its name. Derived profiles <b>MUST</b> use the correct way to indicate derivation in FHIR is using the <code>StructureDefinition.baseDefinition</code> element for example:

```xml
<baseDefinition value="https://fhir.nhs.uk/StructureDefinition/NHSDigital-Immunization"/>
```

This name <b>MUST</b> be used in three places:

- The profile's **filename**.
- The **name** of the profile - specifically the name.value element in the StructureDefinition
- The profile's **logical id**. This is carried in the element <code>StructureDefinition.id.value</code>

**Example of the name Usage**

```xml
    <StructureDefinition xmlns="http://hl7.org/fhir">
    <id value="NHSDigital-MedicationStatement"/>
    <url value="https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationStatement"/>
    <version value="1.0.0"/>
    <name value="NHSDigitalMedicationStatement"/>
```

</div>
</div>

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> 
FHIR-NHSDIGITAL-TITLE-01: (Scope all profiles)</b>

<br/>
<br/>

The title of the profile <b>MUST</b> be the name with added spaces to make it human readable. The FHIR Resource name <b>MUST</b> be formatted as per the FHIR standard.

```xml
 <title value="NHS Digital MedicationStatement" />
 ```
 </div>


<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> 
FHIR-NHSDIGITAL-NAME-03:</b>

<br/>
<br/>

FHIR CodeSystem names <b>MUST</b> follow an agreed format. 

<br/>
<br/>

**Note:** Some ValueSets that use SNOMED CT will refer directly to SNOMED CT artefacts for example SNOMED CT Ref Sets and there will not be a need to create a CodeSystem resource. There many be other ValueSets which follow the same principles for example LOINC.

This section details a set of rules that <b>MUST</b> be followed when creating FHIR CodeSystems. The filename of the CodeSystem consists of a number of name segments and will be in the form:-

**[Base] [BusinessName1] [BusinessName2]**

The segments are defined as follows:-

- **Base**: The base name this will be NHSDigital for NHS Digital CodeSystems or the name of the existing CodeSystem if it is a third party CodeSystem. For example:
  - NHSDigital - CodeSystems managed by the NHS Digital development process/team 
  - NHSDataModelAndDictionary a CodeSystem managed by NHS Data Model and Dictionary
  - For CodeSystems in derived IGs there may not be Base element
- **BusinessName1**: The first business name of the CodeSystem. The CodeSystem name <b>MUST</b> have at least one BusinessName segment,  e.g. 'DigitalMedication', etc. Where a CodeSystem <b>MAY</b> be used across several domains, business names <b>SHOULD</b> reflect that. 
- **BusinessName2**: The second business name of the CodeSystem. The CodeSystem <b>MAY</b> have a second BusinessName segment. 

This name <b>MUST</b> be used as the CodeSystems's filename.

In addition, the CodeSystem's name <b>MUST</b> be used in two places:

- The **name** of the resource - specifically the name.value element
- The resource's **logical ID** in this element a Hyphen is included after each element.

The logical ID forms the final segment of the URL of the CodeSystem resource and is used to populate its logical id (i.e. the <code>CodeSystem.id.value</code> element).

The title of the CodeSystem MUST be the name with added spaces to make it human readable.

```xml
    <title value="NHS Digital Medication Prescribing Agency" />
 ```

**Example of a NHS Digital Codesystem**
``` xml
<CodeSystem xmlns="http://hl7.org/fhir">
    <id value="NHSDigital-MedicationPrescribingAgency" />
    <url value="https://fhir.nhs.uk/CodeSystem/NHSDigital-MedicationPrescribingAgency" />
    <version value="1.0.0" />
    <name value="UKCoreMedicationPrescribingAgency" />
    <title value="UK Core Medication Prescribing Agency" />
```	
**Example of a NHS Data Model and Dictionary CodeSystem**
``` xml
<CodeSystem xmlns="http://hl7.org/fhir">
    <id value="NHSDataModelAndDictionary-PersonStatedGenderCode" />
    <extension url="http://hl7.org/fhir/StructureDefinition/codesystem-sourceReference">
        <valueUri value="" />
    </extension>
    <url value="https://fhir.nhs.uk/CodeSystem/NHSDataModelAndDictionary-PersonStatedGenderCode" />
    <version value="1.0.0" />
    <name value="NHSDataModelandDictionaryPersonStatedGenderCode" />
    <title value="NHS Data Model and Dictionary Person Stated Gender Code" />
```	
</div>
</br>

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> 
FHIR-NHSDIGITAL-NAME-04:</b>

<br/>
<br/>

- NHS Digital FHIR ValueSet names <b>MUST</b> follow an agreed format.

<br/>
<br/>

This section details a set of rules that <b>MUST</b> be followed when creating FHIR ValueSets. The filename of the ValueSet consists of a number of name segments and will be in the form:-

**[Base] [BusinessName1] [BusinessName2]**

- **Base**: a fixed value of "NHSDigital" is <b>Mandatory</b> for all NHS Digital ValueSets
- **BusinessName1**: The first business name of the ValueSet. The ValueSet name <b>MUST</b> have at least one BusinessName segment,  e.g. 'DigitalMedication' , 'SPINE' etc. Where a ValueSet may be used across several domains, business names <b>SHOULD</b> reflect that. 
- **BusinessName2**: The second business name of the ValueSet. The ValueSet <b>MAY</b> have a second BusinessName segment. 

This name <b>MUST</b> be used as the ValueSet's filename.

In addition, The **[BusinessName1]-[BusinessName2] section of the ValueSet's name <b>MUST</b> be used in two places:

- The **name** of the ValueSet - specifically the <code>name.value</code> element
- The resource's **logical ID**.

The logical ID forms the final segment of the URL of the ValueSet resource and is used to populate its logical id (i.e. the <code>ValueSet.id.value</code> element).

**Example of a NHS Digital ValueSet**

```xml
<ValueSet xmlns="http://hl7.org/fhir">
    <id value="NHSDigital-PreferredWrittenCommunicationFormat" />
    <url value="https://fhir.nhs.uk/ValueSet/NHSDigital-PreferredWrittenCommunicationFormat" />
    <version value="1.0.0" />
    <name value="NHSDigitalPreferredWrittenCommunicationFormat" />
    <title value="NHS Digital Preferred Written Communication Format" />
```

</div>
</br>
<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> 
FHIR-NHSDIGITAL-NAME-05:</b>

<br/>
<br/>

FHIR Extension names <b>MUST</b> follow an agreed format.

<br/>
<br/>

The name of the extension consists of a number of name segments and will be in the form:-

FHIR extension names <b>MUST</b> follow an agreed format.

This section details a set of rules that <b>MUST</b> be followed when creating FHIR Extensions. The filename of the Extension consists of a number of name segments and will be in the form:-

**[Base] [BusinessName1] [BusinessName2]**

- **Base**: a fixed value of "NHSDigital" is <b>Mandatory</b> for NHS Digital Extensions
- **BusinessName1**: The first business name of the ValueSet. The Extension name <b>MUST</b> have at least one BusinessName segment,  e.g. 'DigitalMedication' , 'SPINE' etc. Where a Extension may be used across several domains, business names should reflect that. 
- **BusinessName2**: The second business name of the Extension. The Extension <b>MAY</b> have a second BusinessName segment. 

This name <b>MUST</b> be used as the Extension's filename.

In addition, The **[BusinessName1]-[BusinessName2] section of the Extension's name <b>MUST</b> be used in two places:

- The **name** of the Extension - specifically the <code>name.value</code> element
- The resource's **logical ID**.

The logical ID forms the final segment of the URL of the Extension resource and is used to populate its logical id (i.e. the <code>extension.id.value</code> element).

**Example of a NHS Digital Extension**

```xml
<StructureDefinition xmlns="http://hl7.org/fhir">
    <id value="Extension-NHSDigital-ContactPreference" />
    <url value="https://fhir.nhs.uk/StructureDefinition/Extension-NHSDigital-ContactPreference" />
    <version value="2.0.0" />
    <name value="ExtensionNHSDigitalContactPreference" />
    <title value="Extension NHS Digital Contact Preference" />
```
</div>
<br/>
<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> 
FHIR-NHSDIGITAL-NAME-06:</b>

<br/>
<br/>

- FHIR OperationDefinition names <b>MUST</b> follow an agreed format.

<br/>
<br/>

The name of the OperationDefinition will be named using the following segment name format:

**[Base]-[BusinessName]-[OperationAction]-[OperationDefinitionKind]-[Version]**

The segments are defined to as follows:

- **Base**: The base OperationDefinition, if one is used. Optional but <b>Mandatory</b> for UK Core derived OperationDefinitions.
- **BusinessName**: A business name for the OperationDefinition. Optional.
- **OperationAction**: This could include a verb as the first part of the name.  An example would be ‘BookAppointment’.
- **OperationDefinitionKind**: Choice of 'Operation' or 'Query' fixed character strings. <b>Mandatory</b>.

This name <b>MUST</b> be used in three places:

- The OperationDefinition's **filename**.
- The **name** of the resource - specifically the <code>name.value</code> element in the OperationDefinition
- The resource's **logical ID**.

The logical ID forms the final segment of the URL of the OperationDefinition resource and is used to populate its logical id (e.g. the <code>OperationDefinition.id</code> element) when published on the a national FHIR Reference server. An example URL for an OperationDefinition would be <code>https://fhir.nhs.uk/OperationDefinition/PDS-RegisterPatient-Operation</code>, PDS-RegisterPatient-Operation being the value of the logical id.
</div>
<br/>

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> 

FHIR-NAME-06</b> 
<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> 
<br/>

Important note: FHIR identifier systems are to be managed by HL7 UK in partnership with NHS Digital within a simplifier repository. Therefore this section is for information only and more detail will be given once this repository is set up.</b> 
<br/>
FHIR identifier systems <b>MUST</b> follow an agreed format

<br/>
<br/>

Identifier systems may be used in the system element of the Identifier datatype. They establish the namespace for an asset's <code>identifier.value</code> element and have a URI datatype. This section details a set of rules that <b>MUST</b> be followed when creating  FHIR identifier systems. The name of the identifier system consists of a number of name segments and will be in the form:-

**[Base URL]-[Id]-[BusinessName1]-[BusinessName2]-[BusinessName3]-[BusinessName4]**

The segments are defined as follows:-

- **Base URL**: The base URL, which will be in the format <code>https://fhir.hl7.org.uk/</code>for new HL7 defined Naming systems. For pre-existing Naming systems other base URLs may be allowable such as for NHS Digital<code>https://fhir.nhs.uk/</code>. This is <b>Mandatory</b>.
- **Id**: The Id section of the identifier is formatted as a string 'Id'. This segment denotes that the string is an identifier system and is <b>Mandatory</b>.
- **BusinessNames**: The business name segments describe the identifier system. The first business name is <b>Mandatory</b>, but all subsequent ones are optional. There may be up to four business names each separated by a hyphen (-) character e.g. <code>https://fhir.nhs.uk/Id/nhs-number</code>, <code>https://fhir.nhs.uk/Id/sds-role-profile-id</code>.
</div>
</div>
<br/>

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b>FHIR-NAME-07 
</b> 

<br/>
<br/>

The following additional rules <b>MUST</b> also be adhered to for naming FHIR assets:-

- **FHIR-NAME-07A**:  FHIR asset name segments <a>MUST</a> be human understandable. This means that the name must give a clear indication of the purpose or usage of the asset.
- **FHIR-NAME-07B**: NHS Digital FHIR asset names <b>MUST</b> follow the [Pascal Case capitalization] convention and <b>MUST</b> be in alphanumeric format only. In the [Pascal Case capitalization] convention, the first letter in each segment name and of each subsequent compound word must be capitalised e.g. BackColor.
- **FHIR-NAME-07C**: To improve the readability of long NHS Digital FHIR asset names, each string segment used to build an NHS Digital FHIR asset name, <b>MUST</b> be separated using the hyphen (-) character. For example :- Base-BusinessName1-BusinessName2-FHIRAssetName-VersionOfProfile or Base-BusinessName1-FHIRAssetName-VersionOfProfile
- **FHIR-NAME-07D**: CRUD function names <b>MUST NOT</b> be used in NHS Digital FHIR asset names. These are Create, Read, Update and Delete. Other variations should be avoided e.g. Retrieve, Modify, Edit etc.
- **FHIR-NAME-07E**: All acronyms, with the exception of those which form part of an identifier system business name,  <b>MUST</b> be upper case. For example 'NHS' or 'SDS'. Any acronyms used <b>SHOULD</b> be explained in the Implementation Guide glossary.
- **FHIR-NAME-07F**: The order of the BusinessName segments when more than one is used <b>SHOULD</b> be logical and meaningful. For example 'ADW-Accept' should be used instead of 'Accept-ADW'
- **FHIR-NAME-07G**: The asset name <b>MUST</b> have a Version segment. The version number does not have leading or trailing zeros.

**Examples**

- Profile names:
	- UKCore-MessageHeader **VALID**
	- ADW-Encounter **VALID**
	- UkCore-Related-Person **INVALID** (Hyphen in resource name)
	- ITK-Read-Device **INVALID** (CRUD function name)
	- ITK-device **INVALID** (Incorrect capitalisation)
	- ADW-Discharge-Notice-Accept-Response-Message-Header **INVALID** (Too many segments, and hyphen in resource name)
    - UKCore-MessageHeader-1 **INVALID** Version information in the name

- Extension names:
	- Extension-GPC-EthnicCategory **VALID**
	- Extension-ITK-MessageHandling **VALID**
	- ITK-Participant **INVALID** (No FHIRAssetName)

- OperationDefinition names:
	- GPConnect-RegisterPatient-Operation **VALID**
	- eRS-Operation **INVALID** (No OperationConstraint)

- Identifiers:
	- <code>https://fhir.nhs.uk/Id/nhs-number</code> **VALID**
	- <code>https://fhir.nhs.uk/Id/localorganizationcode</code> **INVALID** (No hyphens separating business names)


**Glossary**

**Business name:** Business name is a string used to indicate the usage or purpose of the FHIR asset for a particular implementation or implementations.

[Pascal Case capitalization](https://msdn.microsoft.com/library/ms229043(v=vs.100).aspx)
[FHIR standard](http://hl7.org/fhir/)
[RFC2119](https://www.ietf.org/rfc/rfc2119.txt)
</div>
