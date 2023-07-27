## `Optional Search Parameters`
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

---