## Extensions

<table class="assets">
<tr>
<th width="20%">Extension</th>
<th width="20%">Context</th>
<th width="30%">Comment</th>
</tr>
<tr>
<td>vaccinationProcedure</td>
<td>Immunization</td>
<td>Where status=`completed` this is Mandatory.
This relates to the vaccine that was administered (procedure) and is a SNOMED CT from {{link:https://fhir.hl7.org.uk/ValueSet/UKCore-VaccinationProcedure}}</td>
</tr>
</table>
<br>
In addition to the codes in {{link:https://fhir.hl7.org.uk/ValueSet/UKCore-VaccinationProcedure}}, the following codes are recommended.

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

---