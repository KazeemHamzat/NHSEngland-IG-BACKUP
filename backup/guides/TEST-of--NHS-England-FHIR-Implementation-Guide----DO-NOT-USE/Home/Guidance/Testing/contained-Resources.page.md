## {{page-title}}

Contained resources are not intended to be complete or have independent existence https://www.hl7.org/fhir/references.html#contained. 

As a result of this HL7 FHIR Validation may not work as intended. However, schema/structure validation will be performed and if profiled, they will be validated but the results can be difficult to interpret. 

The recommendation is to validate each contained resource individually first and then validate the parent resource. E.g. If a MedicationRequest contains a Patient resource, validate the Patient resource and resolve issues and then validate the MedicationRequest resource with the contained Patient resource.