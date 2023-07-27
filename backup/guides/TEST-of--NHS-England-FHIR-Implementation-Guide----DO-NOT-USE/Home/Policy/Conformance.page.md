### Conformance


 ### Requirements for FHIR endpoints to declare their capabilities.

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-CONF-01:</b>

<br/>
<br/>

<ul>
<li>All servers offering a FHIR API <b>MUST</b> publish a FHIR conformance / capability statement (in the form of a CapabilityStatement resource) at the root URL of their FHIR Server. Following  {{pagelink:NHSDigital-CapabilityStatement}} profile.</li>
</p>
  </div>
  <br/>

### Requirement for FHIR Payloads to be valid and tested.

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> FHIR-CONF-02:</b>

<br/>
<br/>

<ul>
<li>All API's and/or Servers stating conformance to HL7 FHIR and the UK Core Implementation Guide <b>MUST</b> be validated (/tested) using approved HL7 FHIR Validation tooling. A list of approved validation tooling can be found on {{pagelink:FHIR-Validation}} </li>
<li>NHS Digital API's <b>MUST</b> be validated (/tested) against the NHS Digital Implementation Guide (this guide). This Implementation Guide includes UK Core conformance resources, so separate validation is not required. </li>
</p>
  </div>
  <br/>
