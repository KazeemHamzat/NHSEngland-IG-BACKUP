## {{page-title}}

| Conformance url | FHIR Module | Maturity Level |
|--
| [https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome}) | {{pagelink:Implementation-Support}} | normative |

<br>

### Conformance Rules


<br>

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation"  class="active">
            <a href="#Combined" role="tab" data-toggle="tab">Combined</a>
        </li>
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab">Differential</a>
        </li>
        <li role="presentation">
            <a href="#Constraints" role="tab" data-toggle="tab">Constraints</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
       
        <div id="Combined" role="tabpanel" class="tab-pane active">
            <br>
       with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome, combined}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
        from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome, diff}}
        </div>
        <div id="Constraints"  class="tab-pane">
<br />

@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome'
for differential.element.constraint
select key, human, severity, expression
```

</div>
<div id="Examples"  class="tab-pane">

 - {{pagelink:ValidationErrors}}
 - {{pagelink:OAuth2Issues}}

</div>
</div>

---

### API Error or Warning Codes


@```
from CodeSystem
where url='https://fhir.nhs.uk/CodeSystem/NHSD-API-ErrorOrWarningCode'
for concept
select *
```


<br/>

### Example HL7 FHIR Validation Error

<div class="lang-json">
{{json:England-OperationOutcome-PatientDetailsValidation-Example}}
</div>

<br/>

### Example Data Business Rule Error

<div class="lang-json">
{{json:England-OperationOutcome-PatientDetailsValidation-Example}}
</div>

