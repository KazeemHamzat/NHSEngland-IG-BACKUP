### Serialisation

 <div markdown="span" class="alert alert-warning" role="alert">
 <i class="fas fa-exclamation-triangle"></i><b> Important:</b> Work in progress</div>
 
The FHIR standard allows a number of serialisations of resources to be used. Ideally, servers will support the two main serialisations – XML and JSON, however there may be cases where this is difficult to achieve.

<br/>
<br/>

<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> FHIR-SERIAL-01:</b>

<br/>
<br/>

- FHIR APIs <b>MUST</b> support JSON serialisation.
  - All FHIR endpoints <b>MUST</b> support JSON formatted requests/responses.
  - FHIR endpoints <b>MAY</b> also support XML formatted requests/responses.
  - The serialisation mime-types supported <b>MUST</b> be declared in the   Conformance/CapabilityStatement resource for the endpoint, and the server <b>MUST</b> use the usual FHIR mechanisms to allow clients to request a specific Content Type as per the FHIR spec (servers may choose to reject the use of XML if it is not supported).
  </div>
<br/>


<div markdown="span" class="alert alert-warning" role="alert">
<i class="fas fa-exclamation-triangle"></i><b> FHIR-SERIAL-02:</b>

<br/>
<br/>

- Namespaces outside those defined in the FHIR specification <b>MUST NOT</b> be used.

<br/>
<br/>

The FHIR standard [specifies a specific namespace](http://hl7.org/implement/standards/fhir/xml.html) for FHIR XML elements, with a second namespace for XHTML content in narrative sections. Those specifying FHIR APIs <b>MUST</b> not use other namespaces in their APIs.
</div>

