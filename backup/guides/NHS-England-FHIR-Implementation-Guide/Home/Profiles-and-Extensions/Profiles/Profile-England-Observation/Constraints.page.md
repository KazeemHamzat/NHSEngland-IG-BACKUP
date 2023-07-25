## Constraints (differential)

More information about the constraints on the <code>England-Observation</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>patience-reference</td>
<td>warning</td>
<td>(reference.exists() or (identifier.exists()))</td>
<td>subject - An identifier reference or resource reference must be provided</td>
</tr>
<tr>
<td>patient-nhs</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').value.matches('^([456789]{1}[0-9]{9})$'))</td>
<td>Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.</td>
</tr>
<tr>
<td>performer</td>
<td>error</td>
<td>(reference.exists() or identifier.exists())</td>
<td>An identifier reference or resource reference must be provided</td>
</tr>
</table>

---