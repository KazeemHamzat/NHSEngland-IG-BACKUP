### FHIR Documents

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Experimental. This page is for illustration of a concept</div>

This is the FHIR method of exchanging clinical [documents](https://www.hl7.org/fhir/documents.html). where content to be exchanged is wrapped by a Composition that provides the context of the content, and that has a fixed presentation for a human reader. The document framework is provided to help with computer-assisted human to human communication uses - which are not uncommon in healthcare.

Typically, exchanging documents is associated with exchanging clinical information across NHS organisation and care setting boundaries (e.g., Transfer of Care), while data-based exchange using the RESTful API is appropriate within where there are well established clinical governance arrangements.

The FHIR document is a FHIR Bundle with the type of `document`

| Profile url |
|--
| `https://fhir.nhs.uk/StructureDefinition/NHSDigital-Bundle-FHIRDocument` | 

{{tree:https://fhir.nhs.uk/StructureDefinition/NHSDigital-Bundle-FHIRDocument, diff}}

The FHIR Documents are exchanged using {{pagelink:FHIRMessaging-duplicate-3}} (which is also a FHIR Bundle of type of `message`), as shown in the diagram below:

{{render:fhir-document-bundle}}

The {{pagelink:NHSDigital-Composition}} is subdivided into sections which are equivalent to [PRSB](https://theprsb.org/) headings.