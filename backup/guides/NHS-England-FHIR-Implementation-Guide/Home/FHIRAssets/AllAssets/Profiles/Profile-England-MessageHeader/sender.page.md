## `sender`

<b>Definition</b><br>

 The current requirement in NHS England API's is to rely on the [Access Tokens and Audit (JWT)](https://developer.nhs.uk/apis/spine-core/security_jwt.html) for sender details.

 | | |
|----|----|
|Element Id|MessageHeader.sender|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([England-PractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/England-PractitionerRole) [England-Practitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/England-Practitioner) [England-Organization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/England-Organization))|

<br/>

For use outside of NHS England it is recommended this is populated with either the Organisation ODS code or the Practitioner's professional code.

```json
"sender": {
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
        "value": "VNE51"
   }
}
```

 #### Requirements

 Allows routing beyond just the application level.

 #### Comment

 Use case is for where a (trusted) sending system is responsible for multiple organisations, and therefore cannot differentiate based on source endpoint / authentication alone.

 ---