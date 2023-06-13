## {{page-title}}

The list below contains the element differences between the NHS England and HL7. 

### Base Resource Definitions

View further information about <a href="https://www.hl7.org/fhir/R4/resource.html" Target="_blank">FHIR base resource definitions</a>.   


<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">UK Core Cardinality</th>
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
        <td>In the NHS England the format is the following, with the BusinessName in PascalCase:<br/><br/><code>England-<i>&lsqb;BusinessNames&rsqb;</i></code>.</td>
    </tr>
    </tbody>
</table>

### DomainResource Resource

View further information about <a href="https://www.hl7.org/fhir/R4/domainresource.html" Target="_blank">FHIR domain resources</a>.

<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">UK Core Cardinality</th>
        <th width="15%">Type</th>
        <th width="50%">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>url</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>uri</td>
        <td>In the UK Core the format is the following, with the BusinessName in PascalCase:<br/><br/><code>https://fhir.nhs.uk/CodeSystem/England-<i>&lsqb;BusinessNames&rsqb;</i></code>.</td>
    </tr>
    <tr>
        <td>identifier</td>
        <td>0..*</td>
        <td>0..0</td>
        <td>Identifier</td>
        <td>identifier SHALL NOT be used within the NHS England</td>
    </tr>
    <tr>
        <td>version</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>This will follow the  <a href="https://semver.org/" Target="_blank">Semantic Versioning standard</a> <code><i>&lsqb;major.minor.patch&rsqb;</i></code>.</td>
    </tr>
    <tr>
        <td>name</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the NHS England the format is PascalCase:<br/><br/><code>England<i>&lsqb;BusinessNames&rsqb;</i></code>.</td>
    </tr>
    <tr>
        <td>title</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the NHS England the format is Proper Case:<br/><br/><code>England<i>&lsqb;Business Names&rsqb;</i></code>.</td>
    </tr>
    <tr>
        <td>status</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>See {{pagelink:NamingSystem.status}} for more information.</td>
    </tr>
    <tr>
        <td>date</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>dateTime</td>
        <td>Only the date, without time, is populated in the NHS England.</td>
    </tr>
    <tr>
        <td>publisher</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>For all NHS England CodeSystems, where the base URL is <code>https://fhir.nhs.uk</code>, this will be <code>NHS England</code>.</td>
        <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>See the {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all UK Core CodeSystems, where the base URL is <code> https://fhir.nhs.uk/</code>.</td>
    </tr>
    <tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>The format should be as follows:<br/><br/><samp>A mapping between codes from <i>&lsqb;sourceCodeSystem&rsqb;</i> and codes from <i>&lsqb;targetCodeSystem&rsqb;&quot;</i>.</samp></td>
    </tr>
    <tr>
        <td>copyright</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>All UK Core CodeSystems SHALL contain the the copyright as listed in {{pagelink:Publisher--Contact---Copyright}}</td>
    </tr>
    </tbody>
</table>

### DomainResource Resource

View further information about <a href="https://hl7.org/fhir/R4/conceptmap.html" Target="_blank">FHIR Resource ConceptMap - Content</a>.

<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">UK Core Cardinality</th>
        <th width="15%">Type</th>
        <th width="50%">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>source&lsqb;x&rsqb;</td>
        <td>0..1</td>
        <td>1..1</td>
        <td></td>
        <td>NHS England concept maps use sourceUri. This should be a version specific reference. URIs SHOULD be absolute. If there is no source or target value set, there is no specified context for the map (not recommended). The source value set may select codes from either an explicit (standard or local) or implicit code system.</td>
    </tr>
    <tr>
        <td>target&lsqb;x&rsqb;</td>
        <td>0..1</td>
        <td>1..1</td>
        <td></td>
        <td>NHS England concept maps use targetURI. This should be a version specific reference. URIs SHOULD be absolute. If there is no source or target value set, there is no specified context for the map.</td>
    </tr>
    <tr>
        <td>group<br>.source</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>uri</td>
        <td>Although this is not needed if the source ValueSet is specified and contains concepts from a single CodeSystem, it SHOULD still be included in NHS England concept maps to avoid the need to find the source code system from the value set.</td>
    </tr>
    <tr>
        <td>group<br>.target</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>uri</td>
        <td>Although this is not needed if the target ValueSet is specified and contains concepts from a single CodeSystem, it SHOULD still be included in NHS England concept maps to avoid the needing to find the target code system from the value set. The group.target may be omitted if all of the target element equivalence values are 'unmatched'.</td>
    </tr>
    <tr>
        <td>group<br>.element<br>.code</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>This element SHALL be used in the NHS England.</td>
    </tr>
    <tr>
        <td>group<br>.element<br>.display</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>This element SHALL be used in the NHS England</td>
    </tr>
    <tr>
        <td>group<br>.element<br>.target<br>.display</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>This element SHALL be used in the NHS England</td>
    </tr>
  </tbody>
</table>

---
