## `reason`

<b>Definition</b><br>

reason can be used to subdivide eventCoding. In the example below, cancel is used to indicate the specific reason for the event prescription-order-update. The physical cancellation would be the status=cancelled in the MedicationRequest reason, the reason is a hint.

```json
"reason": {
  "coding":  [
    {
      "system": "https://fhir.nhs.uk/CodeSystem/message-reason-prescription",
      "code": "cancel",
      "display": "Cancel"
    }
  ]
},
```

---