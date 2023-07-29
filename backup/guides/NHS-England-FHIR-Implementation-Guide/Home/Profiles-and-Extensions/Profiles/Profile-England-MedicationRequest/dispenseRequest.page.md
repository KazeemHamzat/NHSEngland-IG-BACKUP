## `dispenseRequest`

Indicates the specific details for the dispense or medication supply part of a medication request (also known as a Medication Prescription or Medication Order). Note that this information is not always sent with the order. There may be in some settings (e.g. hospitals) institutional or system support for completing the dispense details in the pharmacy department.


### `dispenseRequest.validityPeriod`

The `validityPeriod` attribute defines the validity period for the prescription authorisation. This period must start (the `validityPeriod.start`) at the date of prescribing and cannot exceed 12 months (the `validityPeriod.end`). Typically, most repeatable prescriptions will be authorised for a validity period of either 6 or 12 months.

<br>

```json
"dispenseRequest": {
          "validityPeriod": {
            "start": "2020-06-10",
            "end": "2020-12-07"
          },
          ...
      }
```

### `dispenseRequest.numberOfRepeatsAllowed`

An integer indicating the number of times, in addition to the original dispense, (aka refills or repeats) that the patient can receive the prescribed medication. Usage Notes: This integer does not include the original order dispense. This means that if an order indicates dispense 30 tablets plus &;3 repeats&;, then the order can be dispensed a total of 4 times and the patient can receive a total of 120 tablets. A prescriber may explicitly say that zero refills are permitted after the initial dispense.
    
The number of repeat issues authorised if specified. 

**MUST** be present where a `continuous` or `continuous-repeat-dispensing` is authorised for a defined number of issues.

**MUST** NOT be specified where the number of repeat issues has not been defined. Therefore, the numberOfRepeats allowed is the total number of allowed issues. See also extension repeatInformation.

For `continuous` orders and `continuous-repeat-dispensing` with intent=`reflex-order` (i.e., orders sent from EPS to pharmacists) this &lt;b&gt;MUST&lt;/b&gt; be zero. The `numberOfRepeatsAllowed` in the extension to `basedOn` can be used to convey this information to inform patients that they need to re-order the medication. 

Example for a `continuous` issue:

<br>

 ```json 
"dispenseRequest": {
        "numberOfRepeatsAllowed": 0
    }
```

Example for a `continuous-repeat-dispensing` issue with intent of `original-order`: 

 <br>

 ```json 
"dispenseRequest": {
        "numberOfRepeatsAllowed": 2
    }
```
 This will result in a total of three issues of the medication.


### `dispenseRequest.expectedSupplyDuration`

The `expectedSupplyDuration` entity is required for repeat dispensing (repeatable) prescriptions only.

The `expectedSupplyDuration` element defines the expected duration, in days, of each issue of the prescription. A default value of 28 can be used which must be amendable by the prescriber when required. The value must be an integer value greater than zero. A sensible upper limit validation should be included within the System. If this value is omitted, the Spine will assume a value of 28.

<br>

```json
"dispenseRequest": {
          ...
          "expectedSupplyDuration": {
            "value": 28,
            "unit": "days",
            "system": "http://unitsofmeasure.org",
            "code": "d"
          }
      }
```

### `dispenseRequest.performer`

For non token based prescriptions the destination pharmacy **MUST** be recorded in the *dispenseRequest.performer.identifier* and a identifier reference (not a resource reference) with an ANANA/ODS Code **MUST** used. 

The extension 
https://fhir.nhs.uk/StructureDefinition/Extension-England-DMPerformerSiteType         **MUST** be present.

Patients pharmacy preferences may be sourced from PDS.

Patients pharmacy preferences may be overriden by an 'one-off pharmacy nomination' by populating the *dispenseRequest.performer.identifier* with the ODS/ANANA code of the destination pharmacy.

<br>

```json
"dispenseRequest": {
        "extension":  [
            {
                "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PerformerSiteType",
                "valueCoding": {
                    "system": "https://fhir.nhs.uk/CodeSystem/dispensing-site-preference",
                    "code": "0004"
                }
            },
        ],
        "performer": {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "FX748"
            }
        },
```
### `dispenseRequest.performer.extension`

Details of the dispenser who is actioning the MedicationRequest.

<br>

```json
       "dispenseRequest": { 
                    "performer": {
                        "extension":  [
                            {
                                "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-DispensingPerformer",
                                "valueReference": {
                                    "reference": "urn:uuid:25f3dd9f-5838-44a7-930e-c78ae3ecadd6",
                                    "display": "LOTTIE POTTS"
                                }
                            }
                        ],
                        "identifier": {
                            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                            "value": "VNE51"
                        },
                        "display": "The Simple Pharmacy"
                    }
                },
```

---