## `Mandatory Search Parameters`

#### patient:identifier

**SHALL** support searching using the `patient:identifier` search parameter:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Immunization?patient:identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/Immunization?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|9876543210`

`GET [baseUrl]/Immunization?patient:identifier=9876543210`

Return all Immunization resources for Patients with a NHS Number of 9876543210

---