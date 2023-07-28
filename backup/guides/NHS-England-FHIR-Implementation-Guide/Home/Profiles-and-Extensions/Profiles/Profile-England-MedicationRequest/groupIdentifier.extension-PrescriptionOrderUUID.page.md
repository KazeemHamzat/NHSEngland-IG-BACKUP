## `groupIdentifier.extension:PrescriptionOrderUUID`

<b>Definition</b><br>

UUID order number for grouped MedciationRequests

When UUIDs are used within HL7 messages they must be represented in an upper case human-readable hexadecimal format where hyphen separators are used as per the example below and as defined by the ‘datatype’ schema within the DMS.

UUID example (for illustration purposes only **34026084-A445-84AD-2D01-97D69ED25865**.

<br>

```json 
"groupIdentifier": {
    "extension":  [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionId",
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/prescription",
                "value": "ad945a29-85f8-439a-b590-6789719adc16"
            }
        }
    ],
    "system": "https://fhir.nhs.uk/Id/prescription-order-number",
    "value": "DC2C66-A1B2C3-23407B"
}
```

---

