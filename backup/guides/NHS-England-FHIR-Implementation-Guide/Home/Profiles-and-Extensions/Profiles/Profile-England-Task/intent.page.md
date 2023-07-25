## `intent`


| | |
|----|----|
|Element Id|Task.intent|
|<a href="https://www.hl7.org/fhir/conformance-rules.html#cardinality" target="_blank"> Cardinality </a>|1..1|
|<a href="https://www.hl7.org/fhir/terminologies.html" target="_blank"> Terminology Binding </a>|<a href="https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.6.5-prerelease&canonical=http://hl7.org/fhir/ValueSet/task-intent&#124;4.0.1" target="_blank"> TaskIntent </a>(Required) <br/>Distinguishes whether the task is a proposal, plan or full order. |
|<a href="https://www.hl7.org/fhir/datatypes.html" target="_blank"> type </a>|<a href="https://www.hl7.org/fhir/datatypes.html#code" target="_blank"> code </a>|

<br/>

 <b> Definition </b><Br>

 Indicates the "level" of actionability associated with the Task, i.e. i+R[9]Cs this a proposed task, a planned task, an actionable task, etc.

 <b>Comment</b><br>

 Is not processed by EPS and is included for FHIR compliance reasons. The value should always be `order`.

---