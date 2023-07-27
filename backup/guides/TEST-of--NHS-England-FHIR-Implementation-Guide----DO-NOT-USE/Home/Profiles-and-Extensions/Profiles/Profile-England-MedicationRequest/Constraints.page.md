## Constraints (differential)

More information about the constraints on the <code>England-Location</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>eps-1</td>
<td>warning</td>
<td>display.exists()</td>
<td>medication[x] - Only one of medicationReference or medicationCodeableConcept should be provided</td>
</tr>
<tr>
<td>eps-3</td>
<td>warning</td>
<td>display.exists()</td>
<td>requester - An identifier reference or resource reference must be provided</td>
</tr>
<tr>
<td>eps-4</td>
<td>warning</td>
<td>display.exists()</td>
<td>recorder - An identifier reference or resource reference must be provided</td>
</tr>
<tr>
<td>eps-5</td>
<td>warning</td>
<td>display.exists()</td>
<td>Extension(responsiblePractitioner) - An identifier or resource reference must be provided</td>
</tr>
<tr>
<td>eps-7</td>
<td>warning</td>
<td>display.exists()</td>
<td>For continuous-repeat-dispensing intent must be reflex-order or original-order</td>
</tr>
<tr>
<td>eps-8</td>
<td>warning</td>
<td>display.exists()</td>
<td>For continuous intent must be instance-order or original-order</td>
</tr>
<tr>
<td>eps-9</td>
<td>warning</td>
<td>display.exists()</td>
<td>dispenseRequest.numberOfRepeatsAllowed should be populated for continuous and continuous-repeat-dispensing MedicationRequests.</td>
</tr>
<tr>
<td>eps-10</td>
<td>warning</td>
<td>display.exists()</td>
<td>For continuous-repeat-dispensing (intent=reflex-order) basedOn must be populated</td>
</tr>
<tr>
<td>eps-11</td>
<td>warning</td>
<td>display.exists()</td>
<td>For continuous-repeat-dispensing (intent=reflex-order) or continous orders, numberOfRepeatsAllowed must be empty or equal to 0</td>
</tr><tr>
<td>eps-12</td>
<td>warning</td>
<td>display.exists()</td>
<td>For continuous issues basedOn should be populated</td>
</tr>
<tr>
<td>eps-13</td>
<td>warning</td>
<td>display.exists()</td>
<td>Extension repeatInformation.numberOfPrescriptionsIssued should not be present for continuous-repeat-dispensing that are not intent=reflex-order</td>
</tr>
<tr>
<td>eps-14</td>
<td>warning</td>
<td>display.exists()</td>
<td>Extension repeatInformation.numberOfPrescriptionsIssued should be present for continuous-repeat-dispensing that have intent=reflex-order</td>
</tr>
<tr>
<td>eps-15</td>
<td>warning</td>
<td>display.exists()</td>
<td>Extension repeatInformation.numberOfPrescriptionsIssued is recommend to be present for continuous issues</td>
</tr>
<tr>
<td>eps-16</td>
<td>warning</td>
<td>display.exists()</td>
<td>Extension repeatInformation.numberOfPrescriptionsIssued should not be present for acute issues</td>
</tr>
<tr>
<td>patient-nhs</td>
<td>warning</td>
<td>display.exists()</td>
<td>Supplied NHS Number is outside the English and Welish NHS Number range or length of the number is wrong.</td>
</tr>
</table>