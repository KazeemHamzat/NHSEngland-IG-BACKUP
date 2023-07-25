## `dispenseRequest.validityPeriod`

<b>Definition</b><br>

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
  