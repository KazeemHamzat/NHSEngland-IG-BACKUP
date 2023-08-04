## `identifier`

<b>Definition:</b>

**SHOULD** contain a professional code.

The inclusion of a professional code is strongly recommended. For consultants and doctors a prescribing code should be present. Please see [NHS Data Model and Dictionary](https://datadictionary.nhs.uk/) for details on these code.

The *SDS User Id* should be sourced from NHS Identity (SmartCard), this is also held within the Spine Directory Service LDAP database.

| FHIR identifier | OID/HL7v3 | HL7v2 ITK | Format | Description | Professional Code  | Prescribing Code |
| - | - | - | - | - | - | - |
| https://fhir.hl7.org.uk/Id/gmp-number | 2.16.840.1.113883.2.1.3.2.4.16.62 | GMP | G[1234589]NNNNNN | General Medical Practitioner Code [GENERAL MEDICAL PRACTITIONER PPD CODE](https://datadictionary.nhs.uk/attributes/general_medical_practitioner_ppd_code.html). Formerly called GP General National Code (GNC).  | Yes | No, also include DIN |
| https://fhir.hl7.org.uk/Id/gmc-number | 2.16.840.1.113883.2.1.3.2.4.16.63 | GMC | CNNNNNNN |General Medical Council Code [CONSULTANT_CODE](https://datadictionary.nhs.uk/attributes/consultant_code.html) | Yes | Yes |
| https://fhir.hl7.org.uk/Id/nmc-number | | | NNANNNNA |Nursing and Midwifery Council Code | Yes | Yes |
| https://fhir.hl7.org.uk/Id/gphc-number | | | NNNNNNN |General Pharmaceutical Council Code |Yes | Yes  |
| https://fhir.hl7.org.uk/Id/hcpc-number | | | AANNNNNN(*) |Health and Care Professional Council Code |Yes | Yes  |
| https://fhir.hl7.org.uk/Id/din-number | | | NNNNNN | [DOCTOR INDEX NUMBER](https://datadictionary.nhs.uk/attributes/doctor_index_number.html)  | No | Yes |
| https://fhir.nhs.uk/Id/sds-user-id | 1.2.826.0.1285.0.2.0.65 | | N(*)  | SDS User ID | No | No |
| https://fhir.nhs.uk/Id/gmc-reference-number | 2.16.840.1.113883.2.1.3.2.4.18.29 | | NNNNNNN | [GMC Reference Number](https://www.datadictionary.nhs.uk/attributes/general_medical_council_reference_number.html)  | No | No ||
https://fhir.hl7.org.uk/Id/professional-code | 1.2.826.0.1285.0.2.1.54 | | A(*) | ODS/NACS Practitioner Code (retired). Included for backwards compatibility | No | No |

Format
- N = any number
- A = any alpha

(*) NHS Prescription Services systems require these prescriber codes to be 8 characters long. Additional zeroes (0) should be inserted immediately following the first 2 alpha characters to extend the code to 8 characters as necessary.

| Code | Format | Example |
| - | - | - |
| GP/medical prescriber (DIN) | NNNNNN | 954000 |
| Nurse prescriber (NMC) | NNANNNNA | 71A2998E |
| Pharmacist prescriber (GPHC) | NNNNNNN | 2033467 |
| Optometrist prescriber | NN-NNNNN | 01-09491 |
| Podiatrist prescriber (HCPC) | CHNNNNNN | CH029821 |
| Physiotherapist prescriber (HCPC) | PHNNNNNN | PH095159 |
| Radiographer prescriber (HCPC) | RANNNNNN | RA088262 |
| Dietician prescriber (HCPC) | DTNNNNNN | DT012345 |
| Paramedic prescriber (HCPC) | PANNNNNN | PA054321 |

The *Doctor Index Number (DIN)* will be present in the resource even if they are prescribing using a different prescribing code. This code is called the *spurious code* is held within the `England-PractitionerRole` resource and **MUST NOT** be contained in the Practitioner resource. 

### Professional Code System (Unspecified/Unknown System)

In cases where the profession code is present but it is not certain what type of code this is, the `https://fhir.hl7.org.uk/Id/professional-code` system should be used. It is also used for backwards compatibilty with EPS HL7 v3 ODS/NACS Practitioner Identifiers.

This system may include codes from different codes and this may lead to identfication issues, for example GPhC and GMC Reference Number have the same format (7 digits), if one of these is receieved it is not known if this is a doctor and or a pharmacist.

<b>Comment:</b>

SHOULD contain a professional code or SDS-user-id.

### `identifier.gmpCode`

<b>Definition:</b>

Formerly called GP General National Code (GNC).

### `identifier:professionalNumber`

<b>Definition:</b>

A legacy system to support conversion of NPfIT/v3 CodeSysem to FHIR.

This should not be used on new implementations. More accurate systems such as https://fhir.hl7.org.uk/Id/gmp-number and https://fhir.hl7.org.uk/Id/gmc-number

Although this system was intended to only be ODS/NACS Practitioner Identifiers, it has been used as a general purpose system. Therefore the codes can't be trusted e.g. 1234567 could be referring to a GPhC (pharmacist) or GMC Reference Number (doctor). These codes on their won should not be considered safe for the purposes of Practitioner identification.

### `identifier:gmcReferenceNumber`

<b>Definition:</b>

This should not be confused with https://fhir.hl7.org.uk/Id/gmc-number which is the Consultants CONSULTANT_CODE.

This is considered a supplemental code and the official English NHS identifiers (https://fhir.hl7.org.uk/Id/gmc-number or https://fhir.hl7.org.uk/Id/gmp-number) should also be provided.

### `identifier:sdsUserId`

<b>Definition:</b>

Used with CIS2 and Spine.

---

