## NHSDigital-CapabilityStatement

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Experimental. This page is for illustration of a concept</div>

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-CapabilityStatement](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-CapabilityStatement) | {{pagelink:Implementation-Support}} | draft |

<br>

### Conformance Rules


<br>

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation"  class="active">
            <a href="#Combined" role="tab" data-toggle="tab">Combined</a>
        </li>
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab">Differential</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
       
        <div id="Combined" role="tabpanel" class="tab-pane active">
            <br>
       with {{link:http://hl7.org/fhir/StructureDefinition/CapabilityStatement}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-CapabilityStatement, combined}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
        from {{link:http://hl7.org/fhir/StructureDefinition/CapabilityStatement}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-CapabilityStatement, diff}}
        </div>
<div id="Examples"  class="tab-pane">

 - {{pagelink:CapabilityStatement-NHSDigital-IG}}


</div>
</div>

---

<br/>

- <a href="#apiDefinition">apiDefinition</a>
- <a href="#status">status</a>
- <a href="#kind">kind</a>
- <a href="#software">software</a>
- <a href="#fhirVersion">fhirVersion</a>
- <a href="#implementationGuide">implementationGuide</a>
- <a href="#rest">rest</a>
  - <a href="#rest-security">rest.security</a>
  - <a href="#rest-resource">rest.resource</a>
  - <a href="#messaging">messaging</a>

<a name="apiDefinition"></a>
### apiDefinition (extension)

Links to the API documentation **MUST** be provided. 

```json
{
    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-NHSDigital-APIDefinition",
    "extension": [
        {
            "url": "openApi",
            "extension": [
            {
                "url": "documentation",
                "valueUri": "https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir"
            },{
                "url": "description",
                "valueString": "Access the Electronic Prescription Service (EPS) - the national service used to send electronic prescriptions from GP surgeries to pharmacies."
            },
        }
    ]
}
```

A list of Implementation Guide packages used with this API **MUST** be provided.

Although the `UKCore.R4` version can be derived from the  `uk.nhsdigital.r4` package information, it **MUST** be provided. This applies to all derived or supplemental packages.

```json
{
    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-NHSDigital-APIDefinition",
    "extension": [
        {
            "url": "implementationGuide",
            "extension": [
                {
                    "url": "name",
                    "valueString": "uk.nhsdigital.r4"
                },{
                    "url": "version",
                    "valueString": "2.1.34-discovery"
                }
            ]
        },
        {
            "url": "implementationGuide",
            "extension": [
                {
                    "url": "name",
                    "valueString": "UKCore.R4.02.00.00"
                },{
                    "url": "version",
                    "valueString": "2.0.0"
                }
            ]
        }
    ]
}
```
<a name="status"></a>
### status

```json
"status": "active"
```

<a name="kind"></a>
### kind

For APIM FHIR endpoints this **MUST** be `instance`

```json
"kind": "instance"
```

<a name="software"></a>
### software

For APIM FHIR endpoints this is the API Name and verson of the API.

```json
"software": {
    "name": "EPS NextGen",
    "version": "1.2.4-alpha",
    "releaseDate": "2021-07-21T00:00:00+00:00"
}
```

<a name="fhirVersion"></a>
### fhirVersion

For APIM FHIR R4 endpoints this **MUST** be `4.0.1`

```json
"fhirVersion": "4.0.1"
```

<a name="format"></a>
### format

**MUST** be provided. This is populated according to serialisation policies.
{{pagelink:serialisation}}

```json
"format":  [
    "application/fhir+json",
    "application/fhir+xml"
]
```

<a name="implementationGuide"></a>
### implementationGuide

List of FHIR Implementation Guides followed by the API. For NHS Digital APIM endpoints this **MUST** include:

```json
"implementationGuide":  [
        "https://simplifier.net/guide/nhsdigital"
    ],
```


<a name="rest"></a>
### rest 

This is required for all APIM FHIR endpoints.

<a name="rest-security"></a>
### rest.security

Only populated if the endpoint is secured using APIM Apigee security.

*SHOULD include the url of the OAuth2/Apigee endpoint*. Add extension http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris to profile.

```json
"security": {
    "extension": [
        {
            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris",
            "extension": [{
             "url": "token",
                "valueUri": "https://oauth2.nhs.uk/token"
            },{
                "url": "authorize",
                "valueUri": "https://oauth2.nhs.uk/authorize"
            },{
                "url": "manage",
                "valueUri": "https://oauth2.nhs.uk/authorizations/manage"
            }]
        }
    ]
}
```

For APIM FHIR endpoints this should be populated as follows:

```json
"security": {
    "service":  [
        {
            "coding":  [
                {
                    "system": "http://terminology.hl7.org/CodeSystem/restful-security-service",
                    "code": "OAuth",
                    "display": "OAuth2 Token"
                }
            ]
        }
    ]
}
```

<a name="rest-resource"></a>
### rest.resource

All the resources supported by the endpoint **MUST** be listed together with the FHIR profile they conform to. This applies to all FHIR Exchange methods.

```json
"resource":  [
    {
        "type": "CommunicationRequest",
        "profile": "https://fhir.nhs.uk/StructureDefinition/NHSDigital-CommunicationRequest"
    }
]
```


<a name="messaging"></a>
### messaging

**MUST** be populated if FHIR Messaging is used. This **MUST** list all the FHIR MessageDefinitions the endpoint supports.

```json
"messaging":  [
    {
        "supportedMessage":  [
            {
                "mode": "receiver",
                "definition": "https://fhir.nhs.uk/MessageDefinition/prescription-order"
            },
            {
                "mode": "receiver",
                "definition": "https://fhir.nhs.uk/MessageDefinition/dispense-notification"
            }
        ]
    }
]
```

