## NHSDigital-Practitioner


| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner) | {{pagelink:Administration}} | normative |


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
 {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
  from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner, diff}}
        </div>
                <div id="Constraints"  class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples"  class="tab-pane">
<br />

- {{pagelink:Practitioner-duplicate-2}}
- {{pagelink:PractitionerGP}}
- {{pagelink:Practitioner-Nurse}}
- {{pagelink:PractitionerConsultant}}

</div>
</div>

<br/>

 #### Definition

 A person who is directly or indirectly involved in the provisioning of healthcare.

 #### Constraints 

- **prac-nmc** (*WARNING*) NMC must be of the format NNANNNNA
- **prac-gmp** (*WARNING*) GMP must be of the format GNNNNNNN and not be a spurious code (starts with G6 or G7)
- **prac-gmc** (*WARNING*) GMC must be of the format CNNNNNNN
- **prac-gphc** (*WARNING*) GPHC must be of the format NNNNNNN
- **prac-gmcreferencenumber** (*ERROR*) GMC Reference Number must be of the format NNNNNNN
- **prac-hcpc** (*WARNING*) HCPC must be of the format AANNNNNN
- **prac-din** (*WARNING*) DIN format must be NNNNNN
- **prac-sds-user-numeric** (*ERROR*) sds-user-id must be numeric
- **nacs-code-retired** (*WARNING*) NACS (/ODS) Practitioner Identifier is retired in NHS FHIR and should not be used. Please use the actual naming system instead (e,g, https://fhir.hl7.org.uk/Id/gmc-number, https://fhir.hl7.org.uk/Id/gmp-number, etc).


- <a href="#identifier">identifier</a>
- <a href="#identifier:gmcCode">identifier:gmcCode</a>
- <a href="#identifier:gmcCode.system">identifier:gmcCode.system</a>
- <a href="#identifier:gmpCode">identifier:gmpCode</a>
- <a href="#identifier:gmpCode.system">identifier:gmpCode.system</a>
- <a href="#identifier:dinCode">identifier:dinCode</a>
- <a href="#identifier:dinCode.system">identifier:dinCode.system</a>
- <a href="#identifier:gphcCode">identifier:gphcCode</a>
- <a href="#identifier:gphcCode.system">identifier:gphcCode.system</a>
- <a href="#identifier:hcpcNumber">identifier:hcpcNumber</a>
- <a href="#identifier:hcpcNumber.system">identifier:hcpcNumber.system</a>
- <a href="#identifier:nmcNumber">identifier:nmcNumber</a>
- <a href="#identifier:nmcNumber.system">identifier:nmcNumber.system</a>
- <a href="#identifier:professionalNumber">identifier:professionalNumber</a>
- <a href="#identifier:professionalNumber.system">identifier:professionalNumber.system</a>
- <a href="#identifier:gmcReferenceNumber">identifier:gmcReferenceNumber</a>
- <a href="#identifier:gmcReferenceNumber.system">identifier:gmcReferenceNumber.system</a>
- <a href="#identifier:sdsUserId">identifier:sdsUserId</a>
- <a href="#identifier:sdsUserId.system">identifier:sdsUserId.system</a>
- <a href="#name">name</a>
- <a href="#telecom">telecom</a>

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Practitioner.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 **SHOULD** contain a professional code.

The inclusion of a professional code is strongly recommended. For consultants and doctors a prescribing code should be present. Please see [NHS Data Model and Dictionary](https://datadictionary.nhs.uk/) for details on these code.

The *SDS User Id* should be sourced from NHS Identity (SmartCard), this is also held within the Spine Directory Service LDAP database. 


| FHIR identifier | OID/HL7v3 | HL7v2 ITK | Format | Description | Professional Code  | Prescribing Code | 
|--
| https://fhir.hl7.org.uk/Id/gmp-number | 2.16.840.1.113883.2.1.3.2.4.16.62 | GMP | G[1234589]NNNNNN | General Medical Practitioner Code [GENERAL MEDICAL PRACTITIONER PPD CODE](https://datadictionary.nhs.uk/attributes/general_medical_practitioner_ppd_code.html). Formerly called GP General National Code (GNC).  | Yes | No, also include DIN |
| https://fhir.hl7.org.uk/Id/gmc-number | 2.16.840.1.113883.2.1.3.2.4.16.63 | GMC | CNNNNNNN |General Medical Council Code [CONSULTANT_CODE](https://datadictionary.nhs.uk/attributes/consultant_code.html) | Yes | Yes |
| https://fhir.hl7.org.uk/Id/nmc-number | | | NNANNNNA |Nursing and Midwifery Council Code | Yes | Yes |
| https://fhir.hl7.org.uk/Id/gphc-number | | | NNNNNNN |General Pharmaceutical Council Code |Yes | Yes  |
| https://fhir.hl7.org.uk/Id/hcpc-number | | | AANNNNNN(*) |Health and Care Professional Council Code |Yes | Yes  |
| https://fhir.hl7.org.uk/Id/din-number | | | NNNNNN | [DOCTOR INDEX NUMBER](https://datadictionary.nhs.uk/attributes/doctor_index_number.html)  | No | Yes |
| https://fhir.nhs.uk/Id/sds-user-id | 1.2.826.0.1285.0.2.0.65 | | N(*)  | SDS User ID | No | No | 
| https://fhir.nhs.uk/Id/gmc-reference-number | 2.16.840.1.113883.2.1.3.2.4.18.29 | | NNNNNNN | [GMC Reference Number](https://www.datadictionary.nhs.uk/attributes/general_medical_council_reference_number.html)  | No | No | 
| https://fhir.hl7.org.uk/Id/professional-code | 1.2.826.0.1285.0.2.1.54 | | A(*) | ODS/NACS Practitioner Code (retired). Included for backwards compatibility | No | No | 

Format

- N = any number
- A = any alpha

(*) NHS Prescription Services systems require these prescriber codes to be 8 characters
long. Additional zeroes (0) should be inserted immediately following the first 2 alpha
characters to extend the code to 8 characters as necessary.

| Code | Format | Example |
|--
| GP/medical prescriber (DIN) | NNNNNN | 954000 |
| Nurse prescriber (NMC) | NNANNNNA | 71A2998E | 
| Pharmacist prescriber (GPHC) | NNNNNNN | 2033467 |
| Optometrist prescriber | NN-NNNNN | 01-09491 |
| Podiatrist prescriber (HCPC) | CHNNNNNN | CH029821 | 
| Physiotherapist prescriber (HCPC) | PHNNNNNN |PH095159
| Radiographer prescriber (HCPC) | RANNNNNN | RA088262 | 
| Dietician prescriber (HCPC) | DTNNNNNN | DT012345 | 
| Paramedic prescriber (HCPC) | PANNNNNN | PA054321 |

The *Doctor Index Number (DIN)* will be present in the resource even if they are prescribing using a different prescribing code. This code is called the *spurious code* is held within the `NHSDigital-PractitionerRole` resource and **MUST NOT** be contained in the Practitioner resource. 

In the example below, the practitioner (GP as they have a GMP Code) has a SDS User Id of 3415870201, GMP code of G1234567 and DIN code of 123456. If the GP was in a role, prescribing using a spurious code this would be found in the `PractitionerRole`.

```json
{
  "resourceType": "Practitioner",
  ...
  "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/sds-user-id",
            "value": "3415870201"
          },
          {
            "system": "https://fhir.hl7.org.uk/Id/gmp-number",
            "value": "G1234567"
          },
          {
            "system": "https://fhir.hl7.org.uk/Id/din-number",
            "value": "123456"
          }
        ]
  ...
}
```

In the example below, the practitioner (Consultant as they have a GMC Code) has a SDS User Id of 1415870201, GMC code of C2134567.

```json
{
  "resourceType": "Practitioner",
  ...
  "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/sds-user-id",
            "value": "1415870201"
          },
          {
            "system": "https://fhir.hl7.org.uk/Id/gmc-number",
            "value": "C2134567"
          }
        ]
  ...
}
```

### Professional Code System (Unspecified/Unknown System)

In cases where the profession code is present but it is not certain what type of code this is, the `https://fhir.hl7.org.uk/Id/professional-code` system should be used. It is also used for backwards compatibility with EPS HL7 v3 ODS/NACS Practitioner Identifiers. 
This system may include codes from different codes and this may lead to identfication issues, for example GPhC and GMC Reference Number have the same format (7 digits), if one of these is received it is not known if this is a doctor and or a pharmacist.

E.g. in the example below, 2134567 is probably a GMC Reference Number but we are not certain.

```json
{
  "resourceType": "Practitioner",
  ...
  "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/sds-user-id",
            "value": "1415870201"
          },
          {
            "system": "https://fhir.hl7.org.uk/Id/professional-code",
            "value": "2134567"
          }
        ]
  ...
}
```

 #### Requirements

 Often, specific identities are assigned for the agent.

 #### Comment

 SHOULD contain a professional code or SDS-user-id.

<a name="identifier:gmcCode"></a>
 ## identifier:gmcCode

| | |
|----|----|
|Element Id|Practitioner.identifier:gmcCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|gmcCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier that applies to this person in this role.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:gmcCode.system"></a>
 ## identifier:gmcCode.system

| | |
|----|----|
|Element Id|Practitioner.identifier:gmcCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/gmc-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:gmpCode"></a>
 ## identifier:gmpCode

| | |
|----|----|
|Element Id|Practitioner.identifier:gmpCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|gmpCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 Formerly called GP General National Code (GNC).

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:gmpCode.system"></a>
 ## identifier:gmpCode.system

| | |
|----|----|
|Element Id|Practitioner.identifier:gmpCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/gmp-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:dinCode"></a>
 ## identifier:dinCode

| | |
|----|----|
|Element Id|Practitioner.identifier:dinCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|dinCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier that applies to this person in this role.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:dinCode.system"></a>
 ## identifier:dinCode.system

| | |
|----|----|
|Element Id|Practitioner.identifier:dinCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/din-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:gphcCode"></a>
 ## identifier:gphcCode

| | |
|----|----|
|Element Id|Practitioner.identifier:gphcCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|gphcCode|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier that applies to this person in this role.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:gphcCode.system"></a>
 ## identifier:gphcCode.system

| | |
|----|----|
|Element Id|Practitioner.identifier:gphcCode.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/gphc-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:hcpcNumber"></a>
 ## identifier:hcpcNumber

| | |
|----|----|
|Element Id|Practitioner.identifier:hcpcNumber|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|hcpcNumber|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier that applies to this person in this role.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:hcpcNumber.system"></a>
 ## identifier:hcpcNumber.system

| | |
|----|----|
|Element Id|Practitioner.identifier:hcpcNumber.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/hcpc-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:nmcNumber"></a>
 ## identifier:nmcNumber

| | |
|----|----|
|Element Id|Practitioner.identifier:nmcNumber|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|nmcNumber|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier that applies to this person in this role.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:nmcNumber.system"></a>
 ## identifier:nmcNumber.system

| | |
|----|----|
|Element Id|Practitioner.identifier:nmcNumber.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/nmc-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:professionalNumber"></a>
 ## identifier:professionalNumber

| | |
|----|----|
|Element Id|Practitioner.identifier:professionalNumber|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|professionalNumber|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 A legacy system to support conversion of NPfIT/v3 CodeSysem to FHIR.
This should not be used on new implementations. More accurate systems such as https://fhir.hl7.org.uk/Id/gmp-number and https://fhir.hl7.org.uk/Id/gmc-number

Although this system was intended to only be ODS/NACS Practitioner Identifiers, it has been used as a general purpose system. Therefore the codes can't be trusted e.g. 1234567 could be referring to a GPhC (pharmacist) or GMC Reference Number (doctor). These codes on their won should not be considered safe for the purposes of Practitioner identification.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:professionalNumber.system"></a>
 ## identifier:professionalNumber.system

| | |
|----|----|
|Element Id|Practitioner.identifier:professionalNumber.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/professional-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:gmcReferenceNumber"></a>
 ## identifier:gmcReferenceNumber

| | |
|----|----|
|Element Id|Practitioner.identifier:gmcReferenceNumber|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|gmcReferenceNumber|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 This should not be confused with https://fhir.hl7.org.uk/Id/gmc-number which is the Consultants CONSULTANT_CODE. 

This is considered a supplemental code and the official English NHS identifiers (https://fhir.hl7.org.uk/Id/gmc-number or https://fhir.hl7.org.uk/Id/gmp-number) should also be provided.

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:gmcReferenceNumber.system"></a>
 ## identifier:gmcReferenceNumber.system

| | |
|----|----|
|Element Id|Practitioner.identifier:gmcReferenceNumber.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.hl7.org.uk/Id/gmc-reference-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="identifier:sdsUserId"></a>
 ## identifier:sdsUserId

| | |
|----|----|
|Element Id|Practitioner.identifier:sdsUserId|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|sdsUserId|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 Used with CIS2 and Spine

 #### Requirements

 Often, specific identities are assigned for the agent.

<a name="identifier:sdsUserId.system"></a>
 ## identifier:sdsUserId.system

| | |
|----|----|
|Element Id|Practitioner.identifier:sdsUserId.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/sds-user-id|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="name"></a>
 ## name

| | |
|----|----|
|Element Id|Practitioner.name|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[HumanName](https://www.hl7.org/fhir/datatypes.html#HumanName)|

<br/>

 #### Definition

 The name(s) associated with the practitioner.

 #### Requirements

 The name(s) that a Practitioner is known by. Where there are multiple, the name that the practitioner is usually known as should be used in the display.

 #### Comment

 The selection of the use property should ensure that there is a single usual name specified, and others use the nickname (alias), old, or other values as appropriate.    In general, select the value to be used in the ResourceReference.display based on this:  1. There is more than 1 name 2. Use = usual 3. Period is current to the date of the usage 4. Use = official 5. Other order as decided by internal business rules.

<a name="telecom"></a>
 ## telecom

| | |
|----|----|
|Element Id|Practitioner.telecom|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[ContactPoint](https://www.hl7.org/fhir/datatypes.html#ContactPoint)|

<br/>

 #### Definition

 A contact detail for the practitioner, e.g. a telephone number or an email address.

 #### Requirements

 Need to know how to reach a practitioner independent to any roles the practitioner may have.

 #### Comment

 Person may have multiple ways to be contacted with different uses or applicable periods.  May need to have options for contacting the person urgently and to help with identification.  These typically will have home numbers, or mobile numbers that are not role specific.