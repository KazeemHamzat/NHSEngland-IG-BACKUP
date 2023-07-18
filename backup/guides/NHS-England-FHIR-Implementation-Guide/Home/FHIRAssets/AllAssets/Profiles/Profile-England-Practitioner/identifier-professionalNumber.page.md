## `identifier:professionalNumber`

<b>Definition:</b>

A legacy system to support conversion of NPfIT/v3 CodeSysem to FHIR.

This should not be used on new implementations. More accurate systems such as https://fhir.hl7.org.uk/Id/gmp-number and https://fhir.hl7.org.uk/Id/gmc-number

Although this system was intended to only be ODS/NACS Practitioner Identifiers, it has been used as a general purpose system. Therefore the codes can't be trusted e.g. 1234567 could be referring to a GPhC (pharmacist) or GMC Reference Number (doctor). These codes on their won should not be considered safe for the purposes of Practitioner identification.

---

