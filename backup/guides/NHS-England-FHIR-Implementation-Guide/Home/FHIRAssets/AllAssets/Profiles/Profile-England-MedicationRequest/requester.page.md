## `encounter`

<b>Definition</b><br>

The requester must contain a resource reference to the Practitioner who has electronically signed the prescription. If the `requester` can not take responsibility for the prescription, i.e. they would not be the prescriber on the FP10. Then the **extension responsiblePractitioner** must be populated.

<br>

```json

 "requester"{
     "reference": "urn: uuid: 56166769 - c1c4 - 4d07 - afa8 - 132b5dfca666"
 }

````