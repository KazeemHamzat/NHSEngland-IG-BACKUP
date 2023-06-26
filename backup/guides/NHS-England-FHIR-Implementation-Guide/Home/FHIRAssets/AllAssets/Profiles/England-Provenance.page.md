### {{page-title}}


| Conformance url |
|--
| [https://fhir.nhs.uk/StructureDefinition/England-Provenance](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/England-Provenance) | 

<br>

England-Provenance is used to convey the prescription digital signature.

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
          <br><br>
          {{tree: https://fhir.nhs.uk/StructureDefinition/England-Provenance, hybrid}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
         {{tree: https://fhir.nhs.uk/StructureDefinition/England-Provenance, diff}}
        </div>
        <div id="Constraints"  class="tab-pane">
<br/>
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/England-Provenance'
for differential.element.constraint
select key, human, severity, expression
```

</div>
<div id="Examples"  class="tab-pane">
<br/>

-  {{pagelink:Provenance-duplicate-2}}

</div>
</div>

<br/>

- <a href="#target">target</a>
- <a href="#agentwho">agent.who</a>
- <a href="#signaturetype">signature.type</a>
- <a href="#signaturewho">signature.who</a>
- <a href="#signaturewhen">signature.when</a>
- <a href="#signaturedata">signature.data</a>

<br/>

<a name="target"></a>
### target

A resource reference to the target of the Provenance (i.e. the resource being signed)

```json
"target": [
        {
            "type": "MedicationRequest",
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                "value": "a54219b8-f741-4c47-b662-e4f8dfa49ab6"
            }
        }
    ]
```

<br/>

<a name="agentwho"></a>
### agent.who

Actors who have responsibility for the target resource.

It is recommended practitioner professional (e.g. GMC, GMP, etc) and/or organisation ODS codes are used. However SDS id's are permitted.

This **SHOULD** use identifier references. 

```json
"agent": [
        {
            "who": {
                "identifier": {
                    "system": "https://fhir.hl7.org.uk/Id/gmc-number",
                    "value": "C9876543"
                }
            }
        }
    ],
```

<br/>

<a name="signaturetype"></a>
### signature.type

type must be provided. 

```json
"signature": [
        {
            "type": [
                {
                    "system": "urn:iso-astm:E1762-95:2013",
                    "code": "1.2.840.10065.1.12.1.1"
                }
            ]
        }
    ]
```

<br/>

<a name="signaturewhen"></a>
### signature.when

The dateTime the signature was signed. 

```json
"signature": [
        {
            "when": "2008-02-27T11:38:00+00:00"
        }
    ]
```

<br/>

<a name="signaturewho"></a>
### signature.who

A resource reference to a PractitionerRole resource which is normally present in the same FHIR Message. 

```json
"signature": [
        {
            "who": {
                "reference": "urn:uuid:16708936-6397-4e03-b84f-4aaa790633e0"
            }
    ]
```

<br/>

<a name="signaturedata"></a>
### signature.data

Base 64 encoded signature.

```json
"signature": [
        {
            "data": "PFNpZ25hdHVyZSB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC8wOS94bWxkc2lnIyI+PFNpZ25lZEluZm8+PENhbm9uaWNhbGl6YXRpb25NZXRob2QgQWxnb3JpdGhtPSJodHRwOi8vd3d3LnczLm9yZy8yMDAxLzEwL3htbC1leGMtYzE0biMiLz48U2lnbmF0dXJlTWV0aG9kIEFsZ29yaXRobT0iaHR0cDovL3d3dy53My5vcmcvMjAwMC8wOS94bWxkc2lnI3JzYS1zaGExIi8+PFJlZmVyZW5jZT48VHJhbnNmb3Jtcz48VHJhbnNmb3JtIEFsZ29yaXRobT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS8xMC94bWwtZXhjLWMxNG4jIi8+PC9UcmFuc2Zvcm1zPjxEaWdlc3RNZXRob2QgQWxnb3JpdGhtPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwLzA5L3htbGRzaWcjc2hhMSIvPjxEaWdlc3RWYWx1ZT4zWWxGUU1PcncyUTBkVWt5dHpzNTBKRjdIVW89PC9EaWdlc3RWYWx1ZT48L1JlZmVyZW5jZT48L1NpZ25lZEluZm8+PFNpZ25hdHVyZVZhbHVlPlhwanNLWFBmVVc3MDhyR1B1T0FwaGxyNC9VQTIzZjNiaGRCT29jRUoxN0JYVjBKcnV6MUUxS0xGUXdxMzdFSmZuVm8vV0NMVFNqZ2sKa3AwQldqNWJHM0pqRWZqNzhaakkxeVZTUmJmYlZYWFFYMEdMWm1pU0dKcmhXbkZadDhjRnJ4TzFNRkF0U0xtS2Z5WEt6YnVIc0xUbQpzSFFLcFhDUmRabkZtS0JvakxtcDdOQnIwbExFOFBodHR1OEYyRWFldTJ3UFE4NHAxaU5XOTFmbzFIK1NGVnhDK0JSb1BJMXBvbFhnCjQyY2VUam9KNytGcVlQREhmQzduTkZJZ1RZSlpsUWRib01OYm5kdjZCUER1RnEwd3VzUWpEUTR6TVorOENscFJkdDNpS215bFhObUsKa0pBMTVXMHBGYkdxMFhuZjNTMU1YV0Vsa2FDSVVDZEdLMldzUEE9PTwvU2lnbmF0dXJlVmFsdWU+PEtleUluZm8+PFg1MDlEYXRhPjxYNTA5Q2VydGlmaWNhdGU+TUlJRUpEQ0NBd3lnQXdJQkFnSVVLM3hrRVVsUmhYUEpLTlZ3cnlxTFpSb05UUVF3RFFZSktvWklodmNOQVFFTEJRQXdSREVPTUF3RwpBMVVFQ2hNRlNGTkRTVU14RVRBUEJnTlZCQXNUQ0U5d1pXNTBaWE4wTVI4d0hRWURWUVFERXhaRlVGTWdUbTl1TFhKbGNIVmthV0YwCmFXOXVJRU5CTUI0WERUSXdNREl5TnpFek1EY3lNbG9YRFRJeU1ESXlOakV6TURjeU1sb3dPekVPTUF3R0ExVUVDaE1GU0ZORFNVTXgKR3pBWkJnTlZCQXNURWxOdmJIVjBhVzl1SUVGemMzVnlZVzVqWlRFTU1Bb0dBMVVFQXhNRFJVMVZNSUlCSWpBTkJna3Foa2lHOXcwQgpBUUVGQUFPQ0FROEFNSUlCQ2dLQ0FRRUFwMEc0R2FjN1MwbXFsSFkvc1crRUZaWkw4QVUrRk1SclNGSWVmSVNvY0E2RHNIZVBnSHBnCjB0SmNkbWozTjQ1VlI2RkhEckt4NURnLzAwNVIvdDhnYnVJSEYraUkxcHVUY1Y5aldQbWFra3VybFZQQVJtaUF5NzY3V1BrOW1wVW8KbGZvSGRJTEtxZklXTXpRelc3QzRMOHZGSzU1QkllVjQvbElEdkVweForTEhXYmttay9oMWRXZXh1cGpPVGZxVG4vVWl4K0xhdDJUcApxellTck0wYmVwOHA4dWNuZE41c3FjbTZVa1BvdGhzeE5FaTJIamtkOGFvSDFINEtJVndnY0J3V2UrWHJMWEs1V2FyTVcwWTlxZ1FLCnhNc252VzhveUhhODNta0hZK2U4T2VOL1NucVlqa2FnMEk0cHZiQlRjbHJHZklTY0lmVFpvclZuMld2Q0lRSURBUUFCbzRJQkZUQ0MKQVJFd0NRWURWUjBUQkFJd0FEQU9CZ05WSFE4QkFmOEVCQU1DQmFBd0lBWURWUjBsQVFIL0JCWXdGQVlJS3dZQkJRVUhBd0VHQ0NzRwpBUVVGQndNQ01EWUdDV0NHU0FHRytFSUJEUVFwRmlkUGNHVnVkR1Z6ZERvZ1QzQmxibE5UVENCSFpXNWxjbUYwWldRZ1EyVnlkR2xtCmFXTmhkR1V3SFFZRFZSME9CQllFRkFINHB0Y2tPaHNVekJmVmp0L20wNUdpTzhYUk1Ic0dBMVVkSXdSME1IS0FGTklSdlg5b21ybDcKWlhTcUVJTnk2dzJyUFFkdW9VK2tUVEJMTVJRd0VnWURWUVFLRXd0T1NGTWdSR2xuYVhSaGJERVJNQThHQTFVRUN4TUlUM0JsYm5SbApjM1F4SURBZUJnTlZCQU1URjA5d1pXNTBaWE4wSUZKdmIzUWdRWFYwYUc5eWFYUjVnZ2tBNnUwY1hiTHFLb1F3RFFZSktvWklodmNOCkFRRUxCUUFEZ2dFQkFFRGNyUGNkcklDNXVmVkhyYTYyb0dCUC9sejVvSnEzUWw5M1BoZ3c5QkRidW1QVTc0UCtYZ1FvTzl2dzh4TzIKWWI0K1BMN00yQnVKbzNmRHFjRHNXKzRCNHQ5bWRoV1c3bFJqTjNXY3Vqb0xzbFB6MjNjZnl4Q2dabllNTURiT2hCckp4VkN6WWVDNgpueDZPaGtMMVYzWW9lK09JeXJSZVV6cHplQndzVVg1cTgwMmROYVYxeXJiNmFpMmljZ3hxcFkrZk9aWUZMUmVmUElxdXRCSzczaG5ECnV4RGpJKzdlaHlGcGFwZk9YVkJtTFRhY0x4TEYxRHkvNytHSVhiZEl3YmVkZXQ0cDJJY0VhUlgwZVdUMFUvL1pKU2VCcW5PT3BYbzYKNERmWnRTOVZsMmV4SGJISHFZYzBSVk5wS0ltYVdWck15ZEMxcU9leGpVWlNWQlZkK1pvPTwvWDUwOUNlcnRpZmljYXRlPjwvWDUwOURhdGE+PC9LZXlJbmZvPjwvU2lnbmF0dXJlPg=="
        }
    ]
```