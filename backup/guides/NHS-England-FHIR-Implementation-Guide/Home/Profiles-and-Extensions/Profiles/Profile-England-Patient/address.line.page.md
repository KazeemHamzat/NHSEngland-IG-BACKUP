## `address.line`

<b>Definition:</b>

All lines of the address except the postal code.

Systems must apply the following formatting convention when adding or replacing addresses lines:

- line 1 - premises ID and/or house name, e.g. Flat 1 or The Old Schoolhouse
- line 2 - house number, dependent thoroughfare name and descriptor (if present), thoroughfare name and descriptor, e.g. 23 Mill Lane
- line 3 - dependent locality/village, locality (if present), e.g. Boxgrove
- line 4 - post town, e.g. Leeds
- line 5 - county (if present), e.g. West Yorkshire

If any of the lines are blank, they are not returned due to FHIR conformance constraints.

Must contain at most 5 items

---