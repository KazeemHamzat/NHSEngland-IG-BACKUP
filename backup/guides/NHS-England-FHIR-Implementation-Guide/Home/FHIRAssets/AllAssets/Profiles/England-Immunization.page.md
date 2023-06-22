### England-Immunization

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/England-Immunization](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/England-Immunization)  | {{pagelink:Medications}} | trial-use |


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
            Combined with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization}} <br><br>
            {{tree: https://fhir.nhs.uk/StructureDefinition/England-Immunization, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
            {{tree: https://fhir.nhs.uk/StructureDefinition/England-Immunization, diff}}
        </div>
<div id="Constraints" class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/England-Immunization'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples" class="tab-pane">
<br />
<table>
<tr><td>
  {{pagelink:Immunization-history-search}}
</td></tr>
<tr><td>
   {{pagelink:vaccination-covid19-1st-dose}}
</td></tr>
<tr><td>
 {{pagelink:vaccination-covid19-2nd-dose}}  
</td></tr>
<tr><td>
   {{pagelink:vaccination-covid19-not-given}}
</td></tr>
<tr><td>
   {{pagelink:vaccination-covid19-international}}
</td></tr>
</table>
    </div>
</div>

---


<br>

This conformance profile is based on the [NHS England - Daily Clinical Vaccination Specification COVID 19](https://digital.nhs.uk/developer/api-catalogue/vaccination) and is intended for internal use only. 

- <a href="#mustSupport">Must Support, Optional and Should Not Support</a>
- <a href="#vaccinationProcedure">extension vaccinationProcedure</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#vaccineCode">vaccineCode</a>
- <a href="#patient">patient</a>
- <a href="#occurrenceDateTime">occurrenceDateTime</a>
- <a href="#recorded">recorded</a>
- <a href="#primarySource">primarySource</a>
- <a href="#reportOrigin">reportOrigin</a>
- <a href="#location">location</a>
- <a href="#manufacturer">manufacturer</a>
- <a href="#lotNumber">lotNumber</a>
- <a href="#expirationDate">expirationDate</a>
- <a href="#site">site</a>
- <a href="#route">route</a>
- <a href="#doseQuantity">doseQuantity</a>
- <a href="#performer">performer</a>
- <a href="#reasonCode">reasonCode</a>
- <a href="#protocolApplied">protocolApplied</a>
- <a href="#SNOMED CT">SNOMED CT codes relating to COVID-19 Vaccination</a>
- <a href="#search">Search Parameters</a>
  - <a href="#mandatorysearch">Mandatory Search Parameters</a>
  - <a href="#optionalsearch">Optional Search Parameters</a>


<br />

<a name="mustSupport"></a>
### Must Support, Optional and Not Supported

Elements marked with a <span style="background-color:red;color:white;">S</span> **MUST** be supported by both producing and receiving systems. They should be populated if the data exists or the profile has made them mandatory. 

The following elements **SHOULD NOT** are not expected to be supported by consuming or receiving systems.

- `isSubpotent`
- `subpotentReason`
- `education`
- `programEligibility`
- `fundingSource`

Elements that are neither marked as `Must Support` or listed as unsupported are optional. 

<br>

<a name="vaccinationProcedure"></a>
### extension(vaccinationProcedure) <a href="#vaccinationProcedure" title="link to here" class="self-link"><i class="bi-link"></i></a>

Where status=`completed` this is Mandatory
This relates to the vaccine that was administered (procedure) and is a SNOMED CT from {{link:https://fhir.hl7.org.uk/ValueSet/UKCore-VaccinationProcedure}}

In addition to the codes in the following codes are recommended.

<table>
<thead>
<th data-no-sort >
Vaccination Procedure
</th>
<th data-no-sort >
UK SNOMED self
</th>
</thead>
<tr>
<td>
Administration of first dose of SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) vaccine
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=1324681000000101" target="_blank">1324681000000101</a>
</td>
</tr>
<tr>
<td>
Administration of second dose of SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) vaccine
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=1324691000000104" target="_blank">1324691000000104</a>
</td>
</tr>
</table>

<br>

```json
"extension":  [
        {
            "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-VaccinationProcedure",
            "valueCodeableConcept": {
                "coding":  [
                    {
                        "system": "http://snomed.info/sct",
                        "code": "1324681000000101",
                        "display": "Administration of first dose of severe acute respiratory syndrome coronavirus 2 vaccine (procedure)"
                    }
                ]
            }
        }
    ],
```

<br>

<a name="identifier"></a>
### identifier <a href="#identifier" title="link to here" class="self-link"><i class="bi-link"></i></a>

#### identifier.system

A URI for the system that has allocated the vaccination identifier.
Note, this must be unique within a given Supplier system or instance of Supplier system

e.g. 
1) Example of a “single instance for all customers” Supplier system
`https://supplierABC/identifiers/vacc`

2) Example of “per customer instance” Supplier system
`https://supplierABC/ODSCode/NKO41/identifiers/vacc`


#### identifier.value

A unique identifier for the vaccination record, that is consistent between any subsequent update or delete records.

Ideally this would be a GUID / UUID

Value in combination with UNIQUE_ID_URI must be globally unique
In other words, a combination of `identifier.value` and `identifier.system` act as composite primary key to allow lookup of any Adverse Reactions records from the corresponding Adverse Reaction data file.

1) UUID example:
`e045626e-4dc5-4df3-bc35-da25263f901e`

2) Example of a “single instance for all customers” Supplier system
`ACME-vacc123456`

3) Example of “per customer instance” Supplier system
`ACME-CUSTOMER1-vacc123456`
`ACME-CUSTOMER2-vacc123456`

<br>

<a name="status"></a>
### status <a href="#status" title="link to here" class="self-link"><i class="bi-link"></i></a>

For a vaccination that has been administered, the status will be `completed`. This status **does not** indicate a vaccination course has been completed.
When the vaccination has not been administered, the status will be `not-done` and a statusReason should be supplied.

<br>

<a name="vaccineCode"></a>
### vaccineCode <a href="#vaccineCode" title="link to here" class="self-link"><i class="bi-link"></i></a>

Where status is `completed` this is Mandatory. This indicates vaccine product administered. This should be a SNOMED CT code from {{link:https://fhir.hl7.org.uk/ValueSet/UKCore-VaccineCode}}
AMPP codes should not be used.

<table>
<thead>
<th data-no-sort width="20%">
Vaccine Reference Set
</th>
<th data-no-sort width="25%">
UK SNOMED Members Of
</th>
<th data-no-sort width="25%">
UK SNOMED Descendents Of
</th>
</thead>
<tr>
<td>
Meningococcal ACWY vaccines
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000811000001105" target="_blank">999000811000001105</a>
</td>
<td>
</td>
</tr>
<tr>
<td>
Influenza vaccines prescribable within general practice
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=12465201000001105" target="_blank">12465201000001105</a>
</td>
<td>
</td>
</tr>
<tr>
<td>
Meningococcal B vaccines
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000831000001104" target="_blank">999000831000001104</a>
</td>
<td>
</td>
</tr>
<tr>
<td>
Pneumococcal vaccines
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000841000001106" target="_blank">999000841000001106</a>
</td>
<td>
</td>
</tr>
<tr>
<td>
Seasonal Flu vaccines
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000821000001101" target="_blank">999000821000001101</a>
</td>
<td>
</td>
</tr>
<tr>
<td>
COVID-19 vaccines
</td>
<td>
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=39330711000001103" target="_blank">39330711000001103</a>
</td>
</tr>
</table>

<br>

```json
"vaccineCode": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "39114911000001105",
                "display": "COVID-19 Vaccine AstraZeneca (ChAdOx1 S [recombinant]) 5x10,000,000,000 viral particles/0.5ml dose solution for injection multidose vials (AstraZeneca)"
            }
        ]
    },
```

<br>

For EU/international purposes, a vaccination type code can be also be included. The SNOMED CT concept should be from [Vaccines (GPS) - IPS](http://hl7.org/fhir/uv/ips/ValueSet/vaccines-gps-uv-ips) and [EU SNOMED CT Vaccine List (COVID-19)](https://build.fhir.org/ig/hl7-eu/dgc/ValueSet-sct-vaccines-covid-19.html)

```json
"vaccineCode": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "39114911000001105",
                "display": "COVID-19 Vaccine AstraZeneca (ChAdOx1 S [recombinant]) 5x10,000,000,000 viral particles/0.5ml dose solution for injection multidose vials (AstraZeneca)"
            },
            {
                "system": "http://snomed.info/sct",
                "code": "1119305005",
                "display": "SARS-CoV-2 antigen vaccine"
            }
        ]
    },
```

<br>

<a name="patient"></a>
### patient <a href="#patient" title="link to here" class="self-link"><i class="bi-link"></i></a>

A traced NHS Number **SHOULD** be provided and when applicable a resource reference to the Patient resource.

```json
"patient": {
                    "reference": "urn:uuid:edea022a-2d81-11eb-adc1-0242ac120002",
                    "type": "Patient",
                    "identifier": {
                        "system": "https://fhir.nhs.uk/Id/nhs-number",
                        "value": "9912003888"
                    }
                },
```

<br>

<a name="occurrenceDateTime"></a>
### occurrenceDateTime <a href="#occurrenceDateTime" title="link to here" class="self-link"><i class="bi-link"></i></a>

The date and time on which the vaccination intervention was carried out or was meant to be administered.

<br>

<a name="recorded"></a>
### recorded <a href="#recorded" title="link to here" class="self-link"><i class="bi-link"></i></a>

The date that the vaccination administered (procedure) or not administered (situation) was recorded in the source system.

<br>

<a name="primarySource"></a>
### primarySource <a href="#primarySource" title="link to here" class="self-link"><i class="bi-link"></i></a>

Set as TRUE when the content of the record is based on information from the person performing the vaccine or who has clinical responsibility for the vaccination, and the system can be considered a primary source of the vaccination event.
Set as FALSE when the information has NOT come directly from people performing the vaccine (e.g. a patient or patient’s carer), and the system should not be treated as a primary source for this record.
This is used to help identify and eliminate duplicate records held centrally.

<br>

<a name="reportOrigin"></a>
### reportOrigin <a href="#reportOrigin" title="link to here" class="self-link"><i class="bi-link"></i></a>

Where primarySource=`false`, 
-	The ODS code should be set to the location of the primary source of the data where the report of the vaccination event is held
 
Where primarySource=`false` and the vaccination event has been stored in local Primary Care System. 
-	The ODS code should be set to the ODS code of the organisation where the event has been stored e.g. GP practice or PCN.   
Note this field will be used to determine whether or not to send the vaccination event to the patient’s registered GP

```json

"reportOrigin": {
        "text": "RR8 - LEEDS TEACHING HOSPITALS NHS TRUST"
    },
```

<br>

<a name="location"></a>
### location <a href="#location" title="link to here" class="self-link"><i class="bi-link"></i></a>

Country where the vaccination took place. This should follow [Using ISO 3166 Country Codes with FHIR](https://hl7.org/fhir/iso3166.html) or a SNOMED Country Code.

```json

"location": {
        "identifier": {
            "system": "urn:iso:std:iso:3166",
            "value": "FR"
        },
        "display": "France"
    },
```

<br>

<a name="manufacturer"></a>
### manufacturer <a href="#manufacturer" title="link to here" class="self-link"><i class="bi-link"></i></a>

Manufacturer of vaccine product. Only the `display` is expected to be populated.

```json

"manufacturer": {
        "display": "DREAMLAND Pharmaceuticals Ltd"
    },
```

<br>

<a name="lotNumber"></a>
### lotNumber (Batch Number) <a href="#lotNumber" title="link to here" class="self-link"><i class="bi-link"></i></a>

Where status=`completed` this is Mandatory.
This should be captured at source ideally via use of automated scanning technology (GS1 GTIN / NTIN standard).

```json

   "lotNumber": "R04X",
```

<br>

<a name="expirationDate"></a>
### expirationDate <a href="#expirationDate" title="link to here" class="self-link"><i class="bi-link"></i></a>

Shorter date of either:

- Manufacturer expiry date of the vaccine
- Coronavirus point of care sites will only put in the defrost expiry date


<br>

<a name="site"></a>
### site <a href="#site" title="link to here" class="self-link"><i class="bi-link"></i></a>

Body site vaccine was administered into. A SNOMED Concept ID value from UK published reference set “Vaccine body site of administration simple reference set” (1127941000000100) should be used {{link:https://fhir.hl7.org.uk/ValueSet/UKCore-BodySite}}

```json

"site": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "368208006",
                "display": "Left upper arm structure (body structure)"
            }
        ]
    },
```

<br>

<a name="route"></a>
### route <a href="#route" title="link to here" class="self-link"><i class="bi-link"></i></a>

A SNOMED concept ID value from either of the following should be used:
UK “ePrescribing route of administration simple reference set (foundation metadata concept)” (999000051000001100) {{link:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationDosageRoute}}
Or:
UK published reference set “Vaccine route of administration simple reference set” (115231000001104)


```json

 "route": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "78421000",
                "display": "Intramuscular route (qualifier value)"
            }
        ]
    },
```

<br>

<a name="doseQuantity"></a>
### doseQuantity <a href="#doseQuantity" title="link to here" class="self-link"><i class="bi-link"></i></a>

A dm+d (SNOMED) Concept ID value representing the Unit of measure used.

For COVID-19 a reference set has been published here: https://dd4c.digital.nhs.uk/dd4c/publishedmetadatas/intid/980?size=10


```json

 "doseQuantity": {
        "value": 1,
        "unit": "pre-filled disposable injection",
        "system": "http://snomed.info/sct",
        "code": "3318611000001100"
    },
```

<br>

<a name="performer"></a>
### performer (practitioner and organisation) <a href="#performer" title="link to here" class="self-link"><i class="bi-link"></i></a>

The organisation ODS code of the location where the vaccination event took place with corresponding system of `https://fhir.nhs.uk/Id/ods-organization-code`. For roving teams on home visits or care home visits use the site code of the responsible site e.g. GP practice or dedicated vaccination site. It is strongly recommend the name of the Organisation is present in the display field.

Vaccination professional should be recorded using professional codes, see [NHSDigital-Practitioner](https://simplifier.net/guide/nhsdigital/England-Practitioner) for details.


```json

"performer":  [
        {
            "actor": {
                "type": "Practitioner",
                "identifier": {
                    "system": "https://fhir.hl7.org.uk/Id/nmc-number",
                    "value": "5566789"
                },
                "display": "HOLDING, Rafferty"
            }
        },
        {
            "actor": {
                "type": "Organization",
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "C4B2A"
                },
                "display": "ELLAND ROAD STADIUM - COVID VACCINATION CENTRE"
            }
        }
    ],
```


<br>

<a name="reasonCode"></a>
### reasonCode <a href="#reasonCode" title="link to here" class="self-link"><i class="bi-link"></i></a>

A SNOMED Concept Id. For COVID19 and Flu see https://digital.nhs.uk/developer/api-catalogue/vaccination


<br>

<a name="protocolApplied"></a>
### protocolApplied <a href="#protocolApplied" title="link to here" class="self-link"><i class="bi-link"></i></a>
 
`doseNumberPositiveInt` Nominal position in a series of vaccines,
N.B. This field will not always be reliable, therefore for Covid vaccinations, the vaccination procedure code or situation code should be used as that includes the dose number

```json

"protocolApplied":  [
        {
            "doseNumberPositiveInt": 1
        }
    ]
```

<br>

It is recommended for international/EU interoperability `targetDisease` is populated. The SNOMED CT concept should be from [EU COVID-19 Diseases](https://build.fhir.org/ig/hl7-eu/dgc/ValueSet-covid-19-diseases.html) or [Vaccine Target Diseases (GPS) - IPS](http://hl7.org/fhir/uv/ips/ValueSet/targetDiseases-gps-uv-ips)

<table>
<thead>
<th data-no-sort width="20%">
Disease
</th>
<th data-no-sort width="25%">
UK SNOMED self
</th>
</thead>
<tr>
<td>
COVID-19
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=840539006" target="_blank">840539006</a>
</td>
</tr>
<tr>
<td>
Others
</td>
<td>
See <a href="http://hl7.org/fhir/uv/ips/ValueSet/targetDiseases-gps-uv-ips" target="_blank">Vaccine Target Diseases (GPS) - IPS</a>
</td>
</tr>
</table>

<br>

```json

  "protocolApplied": [
    {
        "targetDisease": [
            {
                "coding": [
                    {
                        "system": "http://snomed.info/sct",
                        "code": "840539006",
                        "display": "COVID-19"
                    }
                ]
            }
        ],
        "doseNumberPositiveInt": 1
    }
]

```


<br>

<a name="SNOMEDCT"></a>
### SNOMED CT codes relating to COVID-19 Vaccination <a href="#SNOMEDCT" title="link to here" class="self-link"><i class="bi-link"></i></a>

A complete list of SNOMED CT Codes relating to this profile can be found here [SNOMED CT codes relating to COVID-19 Vaccination](https://hscic.kahootz.com/gf2.ti/f/762498/92769925.1/DOCX/-/COVID19_Vaccination_Codes_20210211_v1.7.docx)

<a name="search"></a>
## Search Parameters <a href="#searchParameters" title="link to here" class="self-link"><i class="bi-link"></i></a>

The following search parameters and search parameter combinations **SHALL** be supported:

- patient:identifier + procedure-code:below

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="15%">Name</th>
     <th data-no-sort width="15%">Type</th>
     <th data-no-sort width="35%">Description</th>
      <th data-no-sort width="15%">Conformance</th>
       <th data-no-sort width="20%">Path</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
date 
    </td>
    <td>
  date
    </td>
     <td>
Vaccination (non-)Administration Date
    </td>
    <td>
SHOULD
    </td>
    <td>
Immunization.date
    </td>
   </tr>    
   <tr>
    <tr>
    <td>
 patient:identifier
    </td>
    <td>
 token
    </td>
     <td>
The patient for the vaccination record
    </td>
    <td>
SHALL
    </td>
    <td>
Immunization.patient
(Patient)
    </td>
   </tr>
    <tr>
    <td>
 procedure-code
    </td>
    <td>
 token
    </td>
     <td>
The target disease and dose number the dose is being administered against
    </td>
    <td>
MAY
    </td>
    <td>
Immunization.extension:vaccinationProcedure
    </td>
   </tr>    
    <tr>
    <td>
 status
    </td>
    <td>
 token
    </td>
     <td>
Immunization event status
    </td>
    <td>
MAY
    </td>
    <td>
Immunization.status
    </td>
   </tr>  
   </tbody>
</table>

<br> 

Additional parameters can be on <a href="https://www.hl7.org/fhir/immunization.html#search" target="_blank">Immunization - Search Parameters</a>


<a name="mandatorysearch"></a>
### Mandatory Search Parameters

#### patient:identifier

**SHALL** support searching using the `patient:identifier` search parameter:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Immunization?patient:identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/Immunization?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|9876543210`

`GET [baseUrl]/Immunization?patient:identifier=9876543210`

Return all Immunization resources for Patients with a NHS Number of 9876543210

<br>

<a name="optionalsearch" /></a>
### Optional Search Parameters

#### date + patient:identifier

**SHOULD** support searching using the combination of the `patient:identifier` and `date` search parameters
- including support for these date comparators: gt,lt,ge,le\- 
- including optional support for composite AND search on date (e.g.date=[date]&date=[date]]&...)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Immunization?patient.identifier={system|}[code]&date=[date]
</div>

Example

`GET [baseUrl]/Immunization?patient:identifier=9876543210&date=ge2010-01-01&date=le2011-12-31`

Return all Immunization resources that have a date greater than or equal to 1st Jan 2010, a date less than or equal to 31st Dec 2011 and Patient with an identifier of 9876543210.

#### procedure-code + patient:identifier

**SHOULD** support searching using the combination of the `patient:identifier` and `procedure-code` search parameters
- including optional support for composite OR search on procedure-code (e.g. procedure-code={system|}[code],{system|}[code],...)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Immunization?patient:identifier={system|}[code]&procedure-code={system|}[code]
</div>

Example:

`GET [baseUrl]/Immunization?patient:identifier=9876543210&procedure-code=http://snomed.info/sct|1324681000000101,1324691000000104`

Return all Immunization resources with a procedure-code of SNOMED CT 1324681000000101 or 1324691000000104 and Patient with a identifier of 9876543210.

#### status + patient:identifier

**SHOULD** support searching using the combination of the `patient:identifier` and `status` search parameters

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Immunization?patient:identifier={system|}[code]&status=[code]
</div>

Example:

To filter on status ( in-progress | on-hold | completed | entered-in-error | stopped )

`GET [baseUrl]/Immunization?patient:identifier=9876543210&status=on-hold`

Return all Immunization resources with a status of on-hold and Patient with a identifier of 9876543210.
