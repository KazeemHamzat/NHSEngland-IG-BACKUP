## {{page-title}}

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/England-MessageHeader](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/England-MessageHeader) | {{pagelink:Implementation-Support}} | trial-use |

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
            <a href="#Constraints" role="tab" data-toggle="tab">Constraints</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
       
        <div id="Combined" role="tabpanel" class="tab-pane active">
            <br>
        with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/England-MessageHeader, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
      from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/England-MessageHeader, diff}}
        </div>
                     <div id="Constraints"  class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/England-MessageHeader'
for differential.element.constraint
select key, human, severity, expression
```
</div>
<div id="Examples"  class="tab-pane">

- {{pagelink:MessageHeader-PrescriptionOrder}}
<br/><br/>

</div>
---
<br/>

 #### Definition

 The header for a FHIR Message exchange that is either requesting or responding to an action. The reference(s) that are the subject of the action as well as other information related to the action are typically transmitted in a bundle in which the MessageHeader resource instance is the first resource in the bundle.

Messaging middleware systems are expected to use this `MessageHeader` resource to route, deliver and handle messages correctly. 

This profile is not tied to any specific transport/API requirement or clinical requirement. Intermediaries are not expected to perform detailed routing on clinical content.
Some clinical information will be required for routing purposes and this will be held within `eventCoding` and `reason` sections as discussed in the Message Event section below. 
In circumstances where more detailed information is required for routing this **MUST** be carried in the relevant FHIR Resource in the payload only. For example, document types should be recorded in FHIR `DocumentReference.type` and health service/specialty type can be recorded in FHIR `Encounter.serviceType` or ` DocumentReference.context.practiceSetting`.


Systems involved in NHSDigital/UKCore messaging are expected to support this profile only, extensions or derived profiles are permitted but they may only have limited (internal) scope and will not be supported outside of this scope (e.g. externally). 
This resource **SHOULD NOT** be profiled to further define the contents of the resources and [FHIR MessageDefinition](https://www.hl7.org/fhir/messagedefinition.html) **MUST** be used instead.

 #### Comment

 <a name="identifiers"></a>
### identifiers and message timings<a href="#identifiers" title="link to here" class="self-link"><i class="bi-link"></i></a>

FHIR messages have two identifiers: the messageIdentifier of the Message (`Bundle.identifier`) and a messageId (`Bundle.id`) which is used in each transport channel . The messageId should be unique within a each message channel/stream. Whenever a message is resent, the messageIdentifier of the Bundle remains the same, but the messageId may change. The response message has its own unique messageIdentifier, the messageIdentifier of the request message can be referenced in the MessageHeader.response.identifier element.

The `Bundle.identifier`, the messageIdentifier, **MUST** have a UUID value.

Systems may chose to map *X-Request-ID* header to the `Bundle.id`, messageId. If both are supplied to a `$process-message` endpoint it is recommended they hold the same values.

MessageHeader can hold previous and extra messageId's in the {{link:https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderMessageID}}

#### Local Part/Addressing (sender and/or destination.receiver)

When exchanging messages between organisations, local references **SHOULD NOT** be used for `sender` and `destination.receiver` references. Local references can make use of the Extension {{link:https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderLocalPart}}. Messages between Organisations should be directed to the Organisation. The receiving organisation will take responsibility for delivering to the local address. Sending organisations are not expected to be able to deliver to local entities in another organisation/domain/facility. 

This concept is similar to email addresses `local-part@domain` and also HL7 version 2 combination of `Sending/Receiving Application | Sending/Receiving Facility` in the MSH segment.

In the example below, the destination is a clinic (A99968) which part of NHS Trust (RBA). Note also the destination endpoint is for the NHS Trust, who will route the message as required. 

```json
"destination": [
    {
        "endpoint": "urn:nhs-uk:addressing:ods:RBA",
        "receiver": {
          "extension": [
              {
                  "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderLocalPart",
                  "valueReference": {
                        "identifier": {
                        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                        "value": "A99968"
                    }
                }

              }
          ],
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "RBA"
            },
            "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
        }
    }
],
```



#### example - Prescription, Pharmacy known

{{render:diagrams-nominatedpharmacy}}

In the example below, the prescriber Taunton and Somerset Foundation Trust (RBA), is sending a message to The Simple Pharmacy (VNE51). The `destination.receiver` and `sender` are references to these organisations.

This message is to be sent via the Electronic Prescription Service, the http address of EPS is held in `destination.endpoint`. Replies to this message can only be received by MESH and the `source.endpoint` is the MESH address of the sending organisation.

```json
"destination": [
    {
        "endpoint": "https://sandbox.api.service.nhs.uk/electronic-prescriptions/$post-message",
        "receiver": {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "VNE51"
            },
            "display": "The Simple Pharmacy"
        }
    }
],
"sender": {
    "identifier": {
        "extension": [
            {
                "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderLocalPart",
                "valueReference": {
                        "identifier": {
                        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                        "value": "A99968"
                    }
                }
            }
        ],
        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
        "value": "RBA"
    },
    "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
},
"source": {
    "endpoint": "urn:nhs-uk:addressing:ods:RBA"
}
```

EPS will now send this message to the pharmacy. This message is collected by the pharmacy using MESH and so the `destination.endpoint` is now the MESH address of the pharmacy. Replies to this message are sent to EPS and so the `source.endpoint` is now the http address of the EPS **$process-message** endpoint.

```json
"destination": [
    {
        "endpoint": "urn:nhs-uk:addressing:ods:VNE51",
        "receiver": {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "VNE51"
            },
            "display": "The Simple Pharmacy"
        }
    }
],
"sender": {
    "extension": [
            {
                "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderLocalPart",
                "valueReference": {
                        "identifier": {
                        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                        "value": "A99968"
                    }
                }

            }
        ],
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
        "value": "RBA"
    },
    "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
},
"source": {
    "endpoint": "https://sandbox.api.service.nhs.uk/electronic-prescriptions/$post-message"
}
```

#### example - Prescription, Pharmacy not known

{{render:diagrams-noNominatedPharmacy}}

In this example the destination is not known and the message is sent to NHS Digital (X26). 

```json
"destination": [
    {
        "endpoint": "https://sandbox.api.service.nhs.uk/electronic-prescriptions/$post-message",
        "receiver": {
    
{{render:diagrams-messageids}}



In addition, a FHIR Message Bundle has two important timestamps:

The time of sending the message is captured in the timestamp element
The last time the message was updated (e.g. by storing or modification) is captured in the meta.lastUpdated element.

```json
{
    "resourceType": "Bundle",
    "id": "884cfa4f-7a56-4be5-9592-783ef4f3992a",
    "meta": {
        "lastUpdated": "2020-11-02T01:43:30+00:00"
      },
    "identifier": {
        "system": "https://tools.ietf.org/html/rfc4122",
        "value": "ad945a29-85f8-439a-b590-6789719adc16"
    },
    "type": "message",
    "timestamp": "2020-11-02T01:43:30+00:00",
    "entry": [
        {
            "fullUrl": "urn:uuid:311316d3-1de0-4f7c-8109-c950ead1c717",
            "resource": {
                "resourceType": "MessageHeader",
                "extension": [
                    {
                        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderMessageID",
                        "valueIdentifier": {
                            "system": "https://fhir.nhs.uk/Id/prescription-order-number",
                            "value": "DC2C66-A1B2C3-23407B"
                        }
                    }
                ]
```


### From (source and sender) and To (destination)


The *From* is contained in both the `sender` and `source` elements and the *To* is contained in the `destination` array. One source, sender and at least one destination **MUST** be present. 

Messages may be sent over multiple transmission legs (i.e. the first leg uses http and the second MESH). The contents of elements **SHOULD** reflect the current leg only.

- destination.endpoint
- source.endpoint
- MessageHeader.extension(messageId)

 Endpoints **MUST** point to valid endpoint uri's on each leg of the messages journey, they may not refer to inaccessible endpoints on other legs. See also the destination section below.

 #### Constraints 

- **nhsd-11** (*WARNING*) replacementOf extension is required for update messages


- <a href="#extension:replacementOf">extension:replacementOf</a>
- <a href="#event[x]">event[x]</a>
- <a href="#destination">destination</a>
- <a href="#sender">sender</a>
- <a href="#sender.identifier">sender.identifier</a>
- <a href="#source">source</a>

<a name="extension:replacementOf"></a>
 ## extension:replacementOf

| | |
|----|----|
|Element Id|MessageHeader.extension:replacementOf|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|replacementOf|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionreplacementOf](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderReplacement))|

<br/>

 #### Definition

 If the message is an update or replaceOf a previous message, then this extension should reference the replaced FHIR Message (Bundle.identifier).

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

<a name="event[x]"></a>
 ## event[x]

| | |
|----|----|
|Element Id|MessageHeader.event[x]|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[England-MessageEvents](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/ValueSet/England-MessageEvents) (Required)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 The main message type is held in the mandatory `eventCoding` section which can be subdivided by the optional `reason` codes.

Every code **MUST** have a corresponding `MessageDefinition`.

For example the event code `dispense-notification` has a MessageDefinition of [https://fhir.nhs.uk/MessageDefinition/pharmacy-dispense](https://simplifier.net/guide/DigitalMedicines/dispense-notification). This definition lists the profiles and cardinality of the resources in the message. `eventCoding` and MessageDefinition define the structure of the message. 

```json
"eventCoding": {
  "system": "https://fhir.nhs.uk/CodeSystem/England-MessageEventEPS",
  "code": "dispense-notification",
  "display": "Dispense Notification"
}
```

 #### Requirements

 Drives the behaviour associated with this message.

 #### Comment

 The time of the event will be found in the focus resource. The time of the message will be found in [Bundle.timestamp](http://hl7.org/fhir/R4/bundle-definitions.html#Bundle.timestamp).

<a name="destination"></a>
 ## destination

| | |
|----|----|
|Element Id|MessageHeader.destination|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 Lists all the destinations where message is be delivered to. 

The recipient of a message takes the responsibility of delivering to all the `destination.endpoint`s. Similarly the sender **MUST NOT** include destination's the recipient can not deliver to, these destinations **MUST** be removed from the message. Additional rules for endpoint can be found in the source section below.

 #### Requirements

 Indicates where message is to be sent for routing purposes.  Allows verification of "am I the intended recipient".

```json
"destination": [
                    {
                        "endpoint": "urn:nhs-uk:addressing:mesh:Y90638OT002",
                        "receiver": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                                "value": "Y9063"
                            }
                        }
                    }
                ]
```

 #### Comment

 There SHOULD be at least one destination, but in some circumstances, the source system is unaware of any particular destination system.

<a name="sender"></a>
 ## sender

| | |
|----|----|
|Element Id|MessageHeader.sender|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([England-PractitionerRole](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/England-PractitionerRole) [England-Practitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/England-Practitioner) [England-Organization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/England-Organization))|

<br/>

 #### Definition

 The current requirement in NHS Engl API's is to rely on the [Access Tokens and Audit (JWT)](https://developer.nhs.uk/apis/spine-core/security_jwt.html) for sender details.

For use outside of NHS Digital it is recommended this is populated with either the Organisation ODS code or the Practitioner's professional code.

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

<a name="sender.identifier"></a>
 ## sender.identifier

| | |
|----|----|
|Element Id|MessageHeader.sender.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 An identifier for the target resource. This is used when there is no way to reference the other resource directly, either because the entity it represents is not available through a FHIR server, or because there is no way for the author of the resource to convert a known identifier to an actual location. There is no requirement that a Reference.identifier point to something that is actually exposed as a FHIR instance, but it SHALL point to a business concept that would be expected to be exposed as a FHIR instance, and that instance would need to be of a FHIR resource type allowed by the reference.

 #### Comment

 When an identifier is provided in place of a reference, any system processing the reference will only be able to resolve the identifier to a reference if it understands the business context in which the identifier is used. Sometimes this is global (e.g. a national identifier) but often it is not. For this reason, none of the useful mechanisms described for working with references (e.g. chaining, includes) are possible, nor should servers be expected to be able resolve the reference. Servers may accept an identifier based reference untouched, resolve it, and/or reject it - see CapabilityStatement.rest.resource.referencePolicy.   When both an identifier and a literal reference are provided, the literal reference is preferred. Applications processing the resource are allowed - but not required - to check that the identifier matches the literal reference  Applications converting a logical reference to a literal reference may choose to leave the logical reference present, or remove it.  Reference is intended to point to a structure that can potentially be expressed as a FHIR resource, though there is no need for it to exist as an actual FHIR resource instance - except in as much as an application wishes to actual find the target of the reference. The content referred to be the identifier must meet the logical constraints implied by any limitations on what resource types are permitted for the reference.  For example, it would not be legitimate to send the identifier for a drug prescription if the type were Reference(Observation|DiagnosticReport).  One of the use-cases for Reference.identifier is the situation where no FHIR representation exists (where the type is Reference (Any).

<a name="source"></a>
 ## source

| | |
|----|----|
|Element Id|MessageHeader.source|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 `source.endpoint` is required and **MUST** indicate the address where replies are to be sent.

For responses to be received via http this will be the address of the `$process-message` endpoint. E.g.

```
https://fhir.hospitaltrust.nhs.uk/$process-message
```

For MESH this will follow [ITK2.2 MESH Transport Requirements](https://data.developer.nhs.uk/architecture/itk/Docs/ITK%20MESH%20Transport%20%20Requirements.pdf) for ITK Routing. E.g. the MESH Endpoint for Organisation B80310 

```
 "source": {
                    "endpoint": "urn:nhs-uk:addressing:mesh:Y90638OT001"
                }
```

 #### Requirements

 Allows replies, supports audit.