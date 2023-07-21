## `supportingInfo`

<b>Definition:</b><br>

Additional clinical information about the patient or specimen that may influence the services or their interpretations. This information includes diagnosis, clinical findings and other observations. In laboratory ordering these are typically referred to as "ask at order entry questions (AOEs)". This includes observations explicitly requested by the producer (filler) to provide context or supporting information needed to complete the order. For example, reporting the amount of inspired oxygen for blood gas measurements.

```json
"supportingInfo": [
        {
            "type" : "DocumentReference",
            "reference": "DocumentReference/5da894e0-a57e-43e9-a1a1-e283a484003c"
        },
        {
            "type" : "QuestionnaireResponse",
            "reference" : "QuestionnaireResponse/d9d4cf80-3f9d-4435-9f3b-e6efb09ad654"
        }
    ],
```

---