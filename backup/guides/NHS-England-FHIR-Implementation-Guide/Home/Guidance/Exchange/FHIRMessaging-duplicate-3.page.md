### FHIR Messaging

This is the FHIR version of traditional [messaging](https://www.hl7.org/fhir/messaging.html). It differs from FHIR [RESTful](https://www.hl7.org/fhir/http.html) in that all the resources are sent to the recipient in one interaction. This is particularly useful between organisations where all the FHIR resources can be sent in one interaction. 

The general FHIR principle that resources **MUST** be self contained still applies. FHIR Messaging should not be used to send highly coupled complex interactions, the message **SHOULD** be easily converted into resource based interactions. A FHIR Message bundle is not a storage based concept, it should be expected that all the resources in the Bundle can be processed individually. Should this be required consider using {{link:fhirdocuments}}

FHIR Messaging should only be used for defined interactions/messages, ad-hoc interactions/collections should use [transactions](https://www.hl7.org/fhir/http.html#transaction)

E.g. in the diagram below a prescription consists of one Patient resource and two MedicationRequests. 
Using FHIR Messaging all the resources are sent within one FHIR Message Bundle. Doing the same with FHIR RESTful would require at least three transactions (possibly more depending on the handling of the Patient resource).

{{render:restvrsfhir1}}

FHIR Message reduces the number of transactions and decouples the sending organisation from local rules. All the resources are handled in a single package and the receiving organisation can handle them according to local procedures. 

FHIR Messaging is very similar to the messaging used in HL7 v2 and HL7 v3 (/ITK), hence the term traditional messaging.

### FHIR Bundle (type=message)

| Profile url |
|--
| `https://fhir.nhs.uk/StructureDefinition/NHSDigital-Bundle-FHIRMessage` | 

{{tree:https://fhir.nhs.uk/StructureDefinition/NHSDigital-Bundle-FHIRMessage, diff}}

This message consists of a Bundle identified by the type "message", with the first resource in the bundle being a MessageHeader resource. The MessageHeader resource has a code - the message event - that identifies the nature of the request message, and it also carries additional request metadata. The other resources in the bundle depend on the type of the request.

For example a `dispense-notification` message will be a FHIR Bundle consisting of 

- one **MessageHeader** resource with an eventCoding `dispense-notification`
- one to four **MedicationDispense** resources
- one (optional) **Patient** resource.

Example `dispense-notifications` can be found in the [NHS Digital Medicines Guide Examples](https://simplifier.net/guide/NHSDigital-Medicines/Home/Examples/AllExamples#Home/Examples/AllExamples/Messagedispense-notification)

These Bundles are send to a `$process-message` operation, e.g. 

POST *baseUrl*/$process-message

In the example above we stated rules for the `dispense-notification` message, these will be contained in a FHIR MessageDefinition and the message definition for this is 
[https://fhir.nhs.uk/MessageDefinition/dispense-notification](https://simplifier.net/guide/NHSDigital-Medicines/Home/FHIRAssets/AllAssets/MessageDefinition-duplicate-2/dispense-notification.guide.md)

{{json:https://fhir.nhs.uk/MessageDefinition/dispense-notification}}

{{render:fhir-message-bundle}}

Some of the key points are:

- **element eventCoding** This is the code that identifies the MessageDefinition and will match the eventingCode in the `dispense-notification` FHIR Message
- **element focus** This lists the principal resources; in the example this is FHIR MedicationDispense resources which follows the [NHSDigital-MedicationDispense](https://simplifier.net/guide/NHSDigital-Medicines/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-MedicationDispense.guide.md) profile. One and up to four resources can be supplied.
- **Patient resource** is not in the focus section. The rule that a Patient resource is required is contained in the FHIR MedicationDispense profile.
- **MessageHeader resource** is not in the focus section. **It is mandatory in all FHIR Messages.**

The FHIR MessageHeader contains the message metadata only and is designed to support message handling without having to process the full message. The use of FHIR MessageHeader with NHSDigital API's is discussed in {{pagelink:NHSDigital-MessageHeader}}. Note this FHIR R4 NHSDigital-MessageHeader is designed to handle all message types and contains rules from both previous MessageHeaders used in Transfer of Care (point to point messages) and National Event Messaging System (pub/sub messages). 









