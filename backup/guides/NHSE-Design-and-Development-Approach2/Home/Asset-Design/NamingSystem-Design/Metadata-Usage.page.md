## {{page-title}}

The list below contains the element differences between the HL7 FHIR R4 and NHS England IG.

### Base Resource Definitions

View further information about <a href="https://www.hl7.org/fhir/R4/resource.html" Target="_blank">FHIR base resource definitions</a>.

<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">NHS England IG Cardinality</th>
        <th width="15%">Type</th>
        <th width="50%">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>id</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>id</td>
        <td>In the NHS England the format is the following, with the Extension name in PascalCase:<br/><br/><code>NamingSystem-England-[Name]</code>.</td>
    </tr>
    </tbody>
</table>

### DomainResource Resource

View further information about <a href="https://www.hl7.org/fhir/R4/domainresource.html" Target="_blank">FHIR domain resources</a>.


To be Edited

<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">NHS England IG Cardinality</th>
        <th width="15%">Type</th>
        <th width="50%">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>name</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In NHS England the format is PascalCase:<br/><br/><code> England[Name]</code>.</td>
    </tr>
    <tr>
        <td>status</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For the NHS England these are defined as: 
        <ul>
        <li>draft - NamingSystem in development</li>
        <li>active - NamingSystem that have been approved via Clinical and Technical Assurance</li>
        <li>retired - NamingSystem that are no longer required</li>
        </ul></td>
    </tr>
    <tr>
        <td>kind</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For the NHS England these are defined as: 
        <ul>
        <li>codesystem - The naming system is used to define concepts and symbols to represent those concepts; e.g. UCUM, LOINC, NDC code, local lab codes, etc.</li>
        <li>identifier - The naming system is used to manage identifiers (e.g. license numbers, order numbers, etc.).</li>
        <li>root - The naming system is used as the root for other identifiers and naming systems.</li>
        </ul></td>
    </tr>
        <td>date</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>dateTime</td>
        <td>Only the date, without time, is populated in NHS England.</td>
    </tr>
    <tr>
        <td>publisher</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>For all NHS England CodeSystems, where the base URL is <code>https://fhir.nhs.uk/England</code>, this will be <code>NHS England</code>.</td>
    </tr>
    <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>Contact details for the publisher.<br/><br/>See the {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all NHS England CodeSystems, where the base URL is <code> https://fhir.nhs.uk/England</code>.</td>
    </tr>
    <tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
         <td>The NHS England IG mandates the use of this element.</td>
    </tr>
    <tr>
        <td>copyright</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>
        All NHS England CodeSystems SHALL contain the the copyright as listed in {{pagelink:Publisher--Contact---Copyright}}</td>
    </tr>
    </tbody>
</table>