## NHSDigital-Patient


| Profile uri | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient) | {{pagelink:Administration}} | normative |

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
        {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
     from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient, diff}}
        </div>
        <div id="Constraints"  class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples"  class="tab-pane">
<br />

- {{pagelink:Patient-JaneSmith}} - PDS Example - Jane Smith
- {{pagelink:Patient-JackDawkins}}
- {{pagelink:Patient-RichardSmith}}

</div>
</div>

### Constraint Profiles

@```
from StructureDefinition
where baseDefinition='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ url + '">'+url+'</a>', purpose
```

---


 This profile is designed around Patient Demographics Services and PDS may be used as the source of this data. 
Use of PDS is not mandatory for Patient resources, Patient Administration Systems (PAS) and Master Patient Index (MPI) may be used instead. Only traced NHS Number SHOULD be used with this resource unless explicitly stated. Within NHS Trusts the inclusion of MRN (Medical Record Numbers) identifiers is highly recommended.

<br/>

 #### Definition

 Demographics and other administrative information about an individual or animal receiving care or other health-related services.

 #### Constraints 

- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<br/>

- <a href="#extension:birthPlace.url">extension:birthPlace.url</a>
- <a href="#extension:cadavericDonor.url">extension:cadavericDonor.url</a>
- <a href="#extension:patientReligion.url">extension:patientReligion.url</a>
- <a href="#extension:patientInterpreterRequired.url">extension:patientInterpreterRequired.url</a>
- <a href="#extension:medicalApplianceSupplier">extension:medicalApplianceSupplier</a>
- <a href="#extension:nominatedPharmacy">extension:nominatedPharmacy</a>
- <a href="#extension:preferredDispenserOrganization">extension:preferredDispenserOrganization</a>
- <a href="#identifier">identifier</a>
- <a href="#identifier:nhsNumber">identifier:nhsNumber</a>
- <a href="#identifier:nhsNumber.system">identifier:nhsNumber.system</a>
- <a href="#name">name</a>
- <a href="#name.family">name.family</a>
- <a href="#name.given">name.given</a>
- <a href="#telecom">telecom</a>
- <a href="#gender">gender</a>
- <a href="#birthDate">birthDate</a>
- <a href="#birthDate.extension:birthTime.url">birthDate.extension:birthTime.url</a>
- <a href="#deceased[x]">deceased[x]</a>
- <a href="#address">address</a>
- <a href="#address.extension:addressKey">address.extension:addressKey</a>
- <a href="#contact">contact</a>
- <a href="#communication">communication</a>
- <a href="#communication.extension:proficiency.extension:level.url">communication.extension:proficiency.extension:level.url</a>
- <a href="#communication.extension:proficiency.extension:type.url">communication.extension:proficiency.extension:type.url</a>
- <a href="#communication.extension:proficiency.url">communication.extension:proficiency.url</a>
- <a href="#generalPractitioner">generalPractitioner</a>
- <a href="#generalPractitioner:registeredGPPractice">generalPractitioner:registeredGPPractice</a>
- <a href="#generalPractitioner:registeredGPPractice.identifier.system">generalPractitioner:registeredGPPractice.identifier.system</a>
- <a href="#generalPractitioner:registeredGeneralMedicalPractitioner">generalPractitioner:registeredGeneralMedicalPractitioner</a>
- <a href="#generalPractitioner:registeredGeneralMedicalPractitioner.identifier.system">generalPractitioner:registeredGeneralMedicalPractitioner.identifier.system</a>
- <a href="#managingOrganization.identifier.system">managingOrganization.identifier.system</a>

<a name="extension:birthPlace.url"></a>
 ## extension:birthPlace.url

| | |
|----|----|
|Element Id|Patient.extension:birthPlace.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://hl7.org/fhir/StructureDefinition/patient-birthPlace|
|[type](https://www.hl7.org/fhir/datatypes.html)|[http://hl7.org/fhirpath/System.String](https://www.hl7.org/fhir/datatypes.html#http://hl7.org/fhirpath/System.String)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="extension:cadavericDonor.url"></a>
 ## extension:cadavericDonor.url

| | |
|----|----|
|Element Id|Patient.extension:cadavericDonor.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://hl7.org/fhir/StructureDefinition/patient-cadavericDonor|
|[type](https://www.hl7.org/fhir/datatypes.html)|[http://hl7.org/fhirpath/System.String](https://www.hl7.org/fhir/datatypes.html#http://hl7.org/fhirpath/System.String)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="extension:patientReligion.url"></a>
 ## extension:patientReligion.url

| | |
|----|----|
|Element Id|Patient.extension:patientReligion.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://hl7.org/fhir/StructureDefinition/patient-religion|
|[type](https://www.hl7.org/fhir/datatypes.html)|[http://hl7.org/fhirpath/System.String](https://www.hl7.org/fhir/datatypes.html#http://hl7.org/fhirpath/System.String)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="extension:patientInterpreterRequired.url"></a>
 ## extension:patientInterpreterRequired.url

| | |
|----|----|
|Element Id|Patient.extension:patientInterpreterRequired.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://hl7.org/fhir/StructureDefinition/patient-interpreterRequired|
|[type](https://www.hl7.org/fhir/datatypes.html)|[http://hl7.org/fhirpath/System.String](https://www.hl7.org/fhir/datatypes.html#http://hl7.org/fhirpath/System.String)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="extension:medicalApplianceSupplier"></a>
 ## extension:medicalApplianceSupplier

| | |
|----|----|
|Element Id|Patient.extension:medicalApplianceSupplier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|medicalApplianceSupplier|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionUKCoreMedicalApplianceSupplier](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicalApplianceSupplier))|

<br/>

 #### Definition

 ```json
{
            "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-PreferredDispenserOrganization",
            "valueReference": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "Y23456"
                }
            }
        }
```

<a name="extension:nominatedPharmacy"></a>
 ## extension:nominatedPharmacy

| | |
|----|----|
|Element Id|Patient.extension:nominatedPharmacy|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|nominatedPharmacy|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionUKCoreNominatedPharmacy](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NominatedPharmacy))|

<br/>

 #### Definition

 A patient can choose up to three nominated dispensers to cover different contractor types:

- Community Pharmacy
- Appliance Contractor
- Dispensing Doctor

Each of those nominations is held in an Extension. 

All require a ODS/ANANA code from [Organisation Data Services](https://digital.nhs.uk/services/organisation-data-service). This contains download CSV files for these organisations, for API access please see  [Organisation Data Service - FHIR API](https://digital.nhs.uk/developer/api-catalogue/organisation-data-service-fhir)

#### nominatedPharmacy (extension nominatedPharmacy)

```json
"extension":  [
        {
            "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NominatedPharmacy",
            "valueReference": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "Y12345"
                }
            }
        },
```

<a name="extension:preferredDispenserOrganization"></a>
 ## extension:preferredDispenserOrganization

| | |
|----|----|
|Element Id|Patient.extension:preferredDispenserOrganization|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|preferredDispenserOrganization|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionUKCorePreferredDispenserOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-PreferredDispenserOrganization))|

<br/>

 #### Definition

 ```json
{
            "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicalApplianceSupplier",
            "valueReference": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "Y34567"
                }
            }
        }
```

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Patient.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 At least one patient identifier, **MUST** be provided. 

Where a traced NHS number is available for a patient this MUST be included. In general an untraced NHS Number **MUST** not be used, if an untracted NHS Number is used the extension https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NHSNumberVerificationStatus **MUST** be used.

| Name | FHIR identifier | OID/HL7v3 | HL7v2 ITK | Format | Description |
|--|--|--|--|--|--|
| NHS Number | https://fhir.nhs.uk/Id/nhs-number | 2.16.840.1.113883.2.1.4.1 |  NHS | NNNNNNNNNN | NHS Number allocated to the patient in England and Wales  |
| CHI Number | | 2.16.840.1.113883.2.1.3.2.4.16.53 | | NNNNNNNNNN | CHI Number allocated to the patient in Scotland |
| NHS Logon ID | https://fhir.nhs.uk/Id/nhs-login-sub | | | uuid | NHS Login unique identifier which is referred to as sub in NHS Login (OpenID) |

Local identifiers such as MRN **MUST** include a *system* which identifies NHS provider/assigning authority. 



```json
"identifier":  [
        {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9000000009"
        },
        {
            "system": "https://fhir.elmet.nhs.uk/Id/MRN",
            "value": "X54321"
        }
    ],
```

 #### Requirements

 Patients are almost always assigned specific numerical identifiers.

<a name="identifier:nhsNumber"></a>
 ## identifier:nhsNumber

| | |
|----|----|
|Element Id|Patient.identifier:nhsNumber|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|nhsNumber|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier for this patient.

 #### Requirements

 Patients are almost always assigned specific numerical identifiers.

<a name="identifier:nhsNumber.system"></a>
 ## identifier:nhsNumber.system

| | |
|----|----|
|Element Id|Patient.identifier:nhsNumber.system|
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

<a name="name"></a>
 ## name

| | |
|----|----|
|Element Id|Patient.name|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[HumanName](https://www.hl7.org/fhir/datatypes.html#HumanName)|

<br/>

 #### Definition

 At least one patient name must be provided. It is recommended a use is provided. 

```json
"name":  [
        {
            "family": "Smith",
            "given":  [
                "Jane"
            ],
            "prefix":  [
                "Mrs"
            ],
            "suffix":  [
                "MBE"
            ],
            "use": "usual"
        }
    ]
```

 #### Requirements

 Need to be able to track the patient by multiple names. Examples are your official name and a partner name.

 #### Comment

 A patient may have multiple names with different uses or applicable periods. For animals, the name is a "HumanName" in the sense that is assigned and used by humans and has the same patterns.

<a name="name.family"></a>
 ## name.family

| | |
|----|----|
|Element Id|Patient.name.family|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 The part of a name that links to the genealogy. In some cultures (e.g. Eritrea) the family name of a son is the first name of his father.

 #### Comment

 Family Name may be decomposed into specific parts using extensions (de, nl, es related cultures).

<a name="name.given"></a>
 ## name.given

| | |
|----|----|
|Element Id|Patient.name.given|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..5|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 Given names, including any middle names.

 #### Comment

 If only initials are recorded, they may be used in place of the full name parts. Initials may be separated into multiple given names but often aren't due to practical limitations.  This element is not called "first name" since given names do not always come first.

<a name="telecom"></a>
 ## telecom

| | |
|----|----|
|Element Id|Patient.telecom|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[ContactPoint](https://www.hl7.org/fhir/datatypes.html#ContactPoint)|

<br/>

 #### Definition

 List of contact points for the patient; for example, phone numbers or email addresses. When a patient tagged as `restricted` or `very restricted` is retrieved, all contact points are removed from the response.

```json
"telecom":  [
        {
            "system": "phone",
            "use": "work",
            "value": "01632960587"
        }
    ]
```

 #### Requirements

 People have (primary) ways to contact them in some way such as phone, email.

 #### Comment

 A Patient may have multiple ways to be contacted with different uses or applicable periods.  May need to have options for contacting the person urgently and also to help with identification. The address might not go directly to the individual, but may reach another party that is able to proxy for the patient (i.e. home phone, or pet owner's phone).

<a name="gender"></a>
 ## gender

| | |
|----|----|
|Element Id|Patient.gender|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[AdministrativeGender](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=http://hl7.org/fhir/ValueSet/administrative-gender&#124;4.0.1) (Required) <br/>The gender of a person used for administrative purposes. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 Classification of the gender of a patient. The classification is phenotypical rather than genotypical, i.e. it does not provide codes for medical or scientific purposes. It is the administrative gender that the patient wishes to be known as. In some cases, this may not be the same as the patient’s registered birth gender, or their current clinical gender.

 #### Requirements

 Needed for identification of the individual, in combination with (at least) name and birth date.

 #### Comment

 The gender might not match the biological sex as determined by genetics or the individual's preferred identification. Note that for both humans and particularly animals, there are other legitimate possibilities than male and female, though the vast majority of systems and contexts only support male and female.  Systems providing decision support or enforcing business rules should ideally do this on the basis of Observations dealing with the specific sex or gender aspect of interest (anatomical, chromosomal, social, etc.)  However, because these observations are infrequently recorded, defaulting to the administrative gender is common practice.  Where such defaulting occurs, rule enforcement should allow for the variation between administrative and biological, chromosomal and other gender aspects.  For example, an alert about a hysterectomy on a male should be handled as a warning or overridable error, not a "hard" error.  See the Patient Gender and Sex section for additional information about communicating patient gender and sex.

<a name="birthDate"></a>
 ## birthDate

| | |
|----|----|
|Element Id|Patient.birthDate|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[date](https://www.hl7.org/fhir/datatypes.html#date)|

<br/>

 #### Definition

 The date on which the patient was born or is officially deemed to have been born.

It is a date in the format `yyyy-mm-dd`. Due to data quality issues on a small number of patients `yyyy-mm` and `yyyy` format may also be returned.

When a patient tagged as `very restricted` is retrieved, birth date is removed from the response.

 #### Requirements

 Age of the individual drives many clinical processes.

 #### Comment

 At least an estimated year should be provided as a guess if the real DOB is unknown  There is a standard extension "patient-birthTime" available that should be used where Time is required (such as in maternity/infant care systems).

<a name="birthDate.extension:birthTime.url"></a>
 ## birthDate.extension:birthTime.url

| | |
|----|----|
|Element Id|Patient.birthDate.extension:birthTime.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://hl7.org/fhir/StructureDefinition/patient-birthTime|
|[type](https://www.hl7.org/fhir/datatypes.html)|[http://hl7.org/fhirpath/System.String](https://www.hl7.org/fhir/datatypes.html#http://hl7.org/fhirpath/System.String)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="deceased[x]"></a>
 ## deceased[x]

| | |
|----|----|
|Element Id|Patient.deceased[x]|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[boolean](https://www.hl7.org/fhir/datatypes.html#boolean)[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 The date and time on which a person died or is officially deemed to have died, if applicable and known.

It is a datetime in the format `yyyy-mm-ddTHH:MM:SS+HH:MM` or `yyyy-mm-dd`. Due to data quality issues on a small number of patients `yyyy-mm` and `yyyy` format may also be returned.

When a patient tagged as `very restricted` is retrieved, death date is removed from the response.

 #### Requirements

 The fact that a patient is deceased influences the clinical process. Also, in human communication and relation management it is necessary to know whether the person is alive.

 #### Comment

 If there's no value in the instance, it means there is no statement on whether or not the individual is deceased. Most systems will interpret the absence of a value as a sign of the person being alive.

<a name="address"></a>
 ## address

| | |
|----|----|
|Element Id|Patient.address|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Address](https://www.hl7.org/fhir/datatypes.html#Address)|

<br/>

 #### Definition

 List of addresses associated with the patient.

These are fully populated on a retrieval or a successful update, only the home address is returned on a search. When a patient tagged as `restricted` or `very restricted` is retrieved, all addresses are removed from the response.

```json
"address":  [
        {
            "line":  [
                "1 Trevelyan Square",
                "Boar Lane",
                "City Centre",
                "Leeds",
                "West Yorkshire"
            ],
            "postalCode": "LS1 6AE",
            "use": "home"
        }
    ],
```

 #### Requirements

 May need to keep track of patient addresses for contacting, billing or reporting requirements and also to help with identification.

 #### Comment

 Patient may have multiple addresses with different uses or applicable periods.

<a name="address.extension:addressKey"></a>
 ## address.extension:addressKey

| | |
|----|----|
|Element Id|Patient.address.extension:addressKey|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|addressKey|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionUKCoreAddressKey](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AddressKey))|

<br/>

 #### Definition

 Postal Address File (PAF) key associated with this address formatted as a FHIR extension. Empty if no PAF key for the address is known, or an object specifying the code system of the address key and the value of the address key.

<a name="contact"></a>
 ## contact

| | |
|----|----|
|Element Id|Patient.contact|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 A list of patient contacts. Only emergency contacts are returned and only emergency contacts should be added. Any other contacts should be added to the patients Related Person. Patients designate here any contact number they desire to be used in case of an emergency. Note, while a patient may also desire to record various related persons telecom details, these do not separately allow for a concept of emergency contact; only ranking. See RelatedPerson endpoint. When a patient tagged as restricted or very restricted is retrieved, all contacts are removed from the response.

 #### Requirements

 Need to track people you can contact about the patient.

 #### Comment

 Contact covers all kinds of contact parties: family members, business contacts, guardians, caregivers. Not applicable to register pedigree and family ties beyond use of having contact.

 #### Constraints 

- **pat-1** (*ERROR*) SHALL at least contain a contact's details or a reference to an organization

<a name="communication"></a>
 ## communication

| | |
|----|----|
|Element Id|Patient.communication|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 A language which may be used to communicate with the patient about his or her health.

 #### Requirements

 If a patient does not speak the local language, interpreters may be required, so languages spoken and proficiency are important things to keep track of both for patient and other persons of interest.

 #### Comment

 If no language is specified, this *implies* that the default local language is spoken.  If you need to convey proficiency for multiple modes, then you need multiple Patient.Communication associations.   For animals, language is not a relevant field, and should be absent from the instance. If the Patient does not speak the default local language, then the Interpreter Required Standard can be used to explicitly declare that an interpreter is required.

<a name="communication.extension:proficiency.extension:level.url"></a>
 ## communication.extension:proficiency.extension:level.url

| | |
|----|----|
|Element Id|Patient.communication.extension:proficiency.extension:level.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|level|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="communication.extension:proficiency.extension:type.url"></a>
 ## communication.extension:proficiency.extension:type.url

| | |
|----|----|
|Element Id|Patient.communication.extension:proficiency.extension:type.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|type|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="communication.extension:proficiency.url"></a>
 ## communication.extension:proficiency.url

| | |
|----|----|
|Element Id|Patient.communication.extension:proficiency.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://hl7.org/fhir/StructureDefinition/patient-proficiency|
|[type](https://www.hl7.org/fhir/datatypes.html)|[http://hl7.org/fhirpath/System.String](https://www.hl7.org/fhir/datatypes.html#http://hl7.org/fhirpath/System.String)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="generalPractitioner"></a>
 ## generalPractitioner

| | |
|----|----|
|Element Id|Patient.generalPractitioner|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPENATEND* discriminator -  *VALUE* *identifier.system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Practitioner) [NHSDigitalPractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole) [NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization))|

<br/>

 #### Definition

 GP Surgery **SHOULD** be provided. It is recommended the patients GP Surgery is the first item in the array and branch surgery is second. It is also suggested type and display (name of practice) is also included. 

```json
"generalPractitioner":  [
        {
            "type": "Organization"
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "Y12345"
            },
            "display": "Kirkgate Practice"
        }
    ]
```

 #### Requirements

 GP Surgery SHOULD be provided. It is recommended the patients GP Surgery is the first item in the array and branch surgery is second. It is also suggested type and display (name of practice) is also included.

 #### Comment

 This may be the primary care provider (in a GP context), or it may be a patient nominated care manager in a community/disability setting, or even organization that will provide people to perform the care provider roles.  It is not to be used to record Care Teams, these should be in a CareTeam resource that may be linked to the CarePlan or EpisodeOfCare resources. Multiple GPs may be recorded against the patient for various reasons, such as a student that has his home GP listed along with the GP at university during the school semesters, or a "fly-in/fly-out" worker that has the onsite GP also included with his home GP to remain aware of medical issues.  Jurisdictions may decide that they can profile this down to 1 if desired, or 1 per type.

 #### Constraints 

- **nhsd-5** (*WARNING*) generalPractitioner - a display name should be provided

<a name="generalPractitioner:registeredGPPractice"></a>
 ## generalPractitioner:registeredGPPractice

| | |
|----|----|
|Element Id|Patient.generalPractitioner:registeredGPPractice|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|registeredGPPractice|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([UKCorePractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner) [UKCoreOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization) [UKCorePractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole))|

<br/>

 #### Definition

 Patient's registered GP Practice. Use V81998 for no registered practice and V81999 for not known as per NHS Data Dictionary guidelines.

 #### Comment

 This may be the primary care provider (in a GP context), or it may be a patient nominated care manager in a community/disability setting, or even organization that will provide people to perform the care provider roles.  It is not to be used to record Care Teams, these should be in a CareTeam resource that may be linked to the CarePlan or EpisodeOfCare resources. Multiple GPs may be recorded against the patient for various reasons, such as a student that has his home GP listed along with the GP at university during the school semesters, or a "fly-in/fly-out" worker that has the onsite GP also included with his home GP to remain aware of medical issues.  Jurisdictions may decide that they can profile this down to 1 if desired, or 1 per type.

<a name="generalPractitioner:registeredGPPractice.identifier.system"></a>
 ## generalPractitioner:registeredGPPractice.identifier.system

| | |
|----|----|
|Element Id|Patient.generalPractitioner:registeredGPPractice.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/Id/ods-organization-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="generalPractitioner:registeredGeneralMedicalPractitioner"></a>
 ## generalPractitioner:registeredGeneralMedicalPractitioner

| | |
|----|----|
|Element Id|Patient.generalPractitioner:registeredGeneralMedicalPractitioner|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|registeredGeneralMedicalPractitioner|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([UKCorePractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner) [UKCoreOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization) [UKCorePractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@2.5.0&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole))|

<br/>

 #### Definition

 This is to support legacy use cases where the patients GP is present

 #### Comment

 This may be the primary care provider (in a GP context), or it may be a patient nominated care manager in a community/disability setting, or even organization that will provide people to perform the care provider roles.  It is not to be used to record Care Teams, these should be in a CareTeam resource that may be linked to the CarePlan or EpisodeOfCare resources. Multiple GPs may be recorded against the patient for various reasons, such as a student that has his home GP listed along with the GP at university during the school semesters, or a "fly-in/fly-out" worker that has the onsite GP also included with his home GP to remain aware of medical issues.  Jurisdictions may decide that they can profile this down to 1 if desired, or 1 per type.

<a name="generalPractitioner:registeredGeneralMedicalPractitioner.identifier.system"></a>
 ## generalPractitioner:registeredGeneralMedicalPractitioner.identifier.system

| | |
|----|----|
|Element Id|Patient.generalPractitioner:registeredGeneralMedicalPractitioner.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/Id/gmp-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="managingOrganization.identifier.system"></a>
 ## managingOrganization.identifier.system

| | |
|----|----|
|Element Id|Patient.managingOrganization.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/Id/ods-organization-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.