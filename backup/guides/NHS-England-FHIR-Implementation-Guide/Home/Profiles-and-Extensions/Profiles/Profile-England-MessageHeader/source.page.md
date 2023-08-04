## `source`

<b>Definition</b><br>

`source.endpoint` is required and **MUST** indicate the address where replies are to be sent.

| | |
|----|----|
|Element Id|MessageHeader.source|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>
For responses to be received via http this will be the address of the `$process-message` endpoint. E.g.

```
https://fhir.hospitaltrust.nhs.uk/$process-message
```

For MESH this will follow [ITK2.2 MESH Transport Requirements](https://data.developer.nhs.uk/architecture/itk/Docs/ITK%20MESH%20Transport%20%20Requirements.pdf) for ITK Routing. E.g. the MESH Endpoint for Organisation B80310 

---