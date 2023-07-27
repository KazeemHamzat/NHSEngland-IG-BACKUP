### Identifiers

 <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Work in progress</div>

In the FHIR standard, every resource has a unique identifier for that resource instance. According to the FHIR specification: “Each resource has an "id" element which contains the logical identity of the resource assigned by the server responsible for storing it.”. This identifier will differ if the resource is moved or persisted on another server (it is analogous to the primary key in a database). Typically, a resource will also have one or more “business” identifiers. These have a business meaning outside the FHIR server (e.g. an NHS number or Organisation Identifier), and can be used in resources held on multiple servers (each instance of which would have different logical IDs to identify them). See: [https://www.hl7.org/fhir/resource.html](https://www.hl7.org/fhir/resource.html)

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-IDENT-01:</b>
<br/><br/>
- Business IDs <b>MUST</b> only be used as the resource ID in RESTful APIs when the system is the authoritative source of that entity.

<br/>
<br/>

In some cases, where a system is acknowledged as the authoritative source of reference for a particular class of information, the need to do a lookup using a business ID to identify the logical ID of a resource may not be desirable. Equally, where the business ID is actually the primary key in a system for which the FHIR RESTful API is simply a facade, generating another synthetic ID may not add any real value. In these cases, and ONLY in these cases, the business ID <b>MAY</b> be used as the logical ID for the resource exposed in a FHIR ReST API.
Currently, the only national resources this would apply to are:

- [Organisation](https://simplifier.net/guide/NHSDigital/NHSDigital-Organization#identifier) (ODS Code)
- [Patient](https://simplifier.net/guide/NHSDigital/NHSDigital-Patient#identifier) (NHS Number)
- Prescription ([Prescription ID](https://simplifier.net/guide/digitalmedicines/NHSDigital-MedicationRequest#identifier))
- Referrals/ServiceRequest (National eReferral request (UBRN))

Clients must never assume a specific ID format when querying for resources.

Where resources include references to other resources, there is also a need to consider how these references would be represented to ensure clients are able to follow them and find referenced resources. The preferred approach to this differs depending on the FHIR Paradigm used:
</div>

<br/>
<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-IDENT-02:</b>

<br/>
<br/>

- FHIR Documents <b>SHOULD</b> contain any referenced resources.

<br/>
<br/>

When using the FHIR Document Paradigm, wherever possible referenced resources should always be contained in the composition so that recipients have all the information needed to interpret and act on the content of the document. This also means that the recipient is confident that all included resources are the versions that were the latest at the time the document was created. Within a document, resources can reference each other, these references are meaningless outside the document however. Note: References between resources within a document can include circular references – this should be taken into account when parsing.
</div>
<br/>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-IDENT-03:</b>
<br/>
<br/>
- References in FHIR messaging <b>SHOULD</b> be logical references.

<br/>
<br/>

When using the FHIR Messaging Paradigm, it is likely messages will include references to external resources. These references <b>SHOULD</b> use an identifier from a known NamingSystem. This is known as a [logical reference](https://www.hl7.org/fhir/references.html#logical) in the FHIR standard. The NamingSystem URI SHOULD be searchable on a FHIR Reference server to return the NamingSystem resource that describes the identifiers used (for example: [https://fhir.nhs.uk/NamingSystem](https://fhir.nhs.uk/NamingSystem)).


An example of a logical reference would be the below (for an ODS code):

```json
{
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
        "value": "RBA"
    },
    "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
}
```
</div>
<br/>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-IDENT-04:</b>

<br/>
<br/>

- References between RESTful resources <b>SHOULD</b> be literal references but <b>MAY</b> be logical references.

<br/>
<br/>

When using the FHIR RESTful Paradigm, resources SHOULD reference other resources via URL (i.e. a [literal reference](https://www.hl7.org/fhir/references.html#literal) in the FHIR standard). The resource owner should (where possible) only reference other resources that they can be relatively confident consumers of their API will be able to resolve and retrieve. For referencing other things outside this, a logical reference SHOULD be used.

<b>Note:</b> URL references to other resources will (by default) return the latest version of the referenced resource. If this isn't desirable, the resource owner may either contain the resource or use a versioned URL as a literal reference.

An example of a literal reference would be the below (also for an ODS code):

```json
{
    "reference": "https://directory.spineservices.nhs.uk/R4/Organization/RBA",
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
        "value": "RBA"
    },
    "display": "TAUNTON AND SOMERSET NHS FOUNDATION TRUST"
}
```
</div>