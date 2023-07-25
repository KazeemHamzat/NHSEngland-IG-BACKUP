## `response`

<b>Definition</b><br>

If the message is a response to a previous message, the response.identifier MUST match the previous request messages Bundle.identifier Correlation-ID.

```json
"response": {
    "identifier": "ad945a29-85f8-439a-b590-6789719adc16",
    "code": "ok"
},
```
---