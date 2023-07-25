## `dispenseRequest.expectedSupplyDuration`

<b>Definition</b><br>

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
 