### Release Notes

  <div markdown="span" class="alert alert-warning" role="alert"
  <i class="fas fa-exclamation-triangle"></i><b> Important:</b> This page is under development by NHS Digital</div>


 ### 2.8.0

- UKCore fhir.r4.ukcore.stu3.currentbuild 0.0.3-pre-release

 ### 2.7.0

- UKCore fhir.r4.ukcore.stu1 version 1.0.0-pre-release
- Removal of BARS Conformance resources. 

 ### 2.6.0

 - UKCore fhir.r4.ukcore.stu1 version 0.5.1
 - Support for HL7 FHIR Validation command line and online tools. See {{pagelink:FHIR-Validation}}
 - Alignment of the IG to FHIR Modules
 - Addition of NHS App CodeSystem
   - NHSApp-Communication-Status
 - Addition of BARS CodeSystems
   - DOS Id BARS
   - Household Composition BARS
   - Flag Categories BARS
   - DOS Rejected Reasons BARS
   - Consent Categories BARS
   - Reasonable Adjustment Codes BARS
   - Safeguarding Codes BARS
   - Scene Safety Codes BARS
   - Message Events BARS
   - Message Reason BARS
   - HttpErrorCodes
 - Addition of BARS MessageDefinition and Profiles   
 - EPS Changes
   - Constraint profiles updated to support ODS API Lookup removal
     - [NHSDigitalOrganizationSDS](https://simplifier.net/nhsdigital/nhsdigitalorganizationsds)
     - [NHSDigitalPractitionerRoleSDS](https://simplifier.net/nhsdigital/nhsdigitalpractitionerrolemessage)
   - New URI to support retiring of UKCore-SDSJobRoleName [https://fhir.nhs.uk/CodeSystem/NHSDigital-SDS-JobRoleCode](https://simplifier.net/nhsdigital/ukcore-sdsjobrolename)
 - NHSDigital-Practitioner now includes guidance on gmc-reference-number and legacy NACS/ODS Practitioner Identifiers.
 - eRS support for the wayfinder project. 
   - [NHSDigital-AppointmentPatientCare](https://simplifier.net/nhsdigital/nhsdigitalappointmentpatientcare)
   - [NHSDigital-TaskPatientCare](https://simplifier.net/nhsdigital/nhsdigitaltaskpatientcare)
   - [NHSDigitalServiceRequestPatientCare](https://simplifier.net/nhsdigital/nhsdigitalservicerequestpatientcare)
   - [NHSDigitalHealthcareServicePatientCare](https://simplifier.net/nhsdigital/nhsdigitalhealthcareservicepatientcare)

 ### 2.5.0

[NHS Digital version 2.5.0](https://simplifier.net/guide/nhsdigital/Home?version=2.5.0) 

 - UKCore fhir.r4.ukcore.stu1 version 0.5.0
 - Support for eRS


 ### 2.3.0



 - Based on UK Core Implementation Guide 0.1.0 - STU1 (ukcore.release1.stu1.01.01)
 - Numerous examples changed following FHIR Validation
 - Support for COVID Exemption API
 - Task.reasonCode altered to prefer SNOMED CT concepts
 - Profiling of NHSDigital-MessageHeader relaxed.
 - NHSDigital-PractitionerRole and NHSDigital-Practitioner now has constraint rules.
 - NHSDigital-Patient now has constraint rules
 - NHSDigital-Observation COVID Test pillar corrections
 - sds-user-id now optional in NHSDigital-Practitioner
 

  ### 2.1.42-discovery

  NHSDigital-Patient extension https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NHSCommunication has been removed from the profile as it is no longer supported in UKCore.
  