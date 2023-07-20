## `extension:replacementOf`

<b>Definition:</b><br>

If the message is an update or replaceOf a previous message, then this extension should reference the replaced FHIR Message (Bundle.identifier).

| | |
|----|----|
|Element Id|MessageHeader.extension:replacementOf|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|replacementOf|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionreplacementOf](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderReplacement))|

```json
"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderReplacement",
        "valueIdentifier": {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "334a3195-1f6c-497a-8efe-d272ca9c4e38"
        }
    }
],
```
---
