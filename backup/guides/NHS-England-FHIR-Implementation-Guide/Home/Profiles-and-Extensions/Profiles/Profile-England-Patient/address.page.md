## `address`

<b>Definition:</b>

List of addresses associated with the patient.

These are fully populated on a retrieval or a successful update, only the home address is returned on a search. When a patient tagged as `restricted` or `very restricted` is retrieved, all addresses are removed from the response.

```json
"address":  [
{
  "line":  [
    "1 Trevelyan Square",
    "Boar Lane",
    "City Centre",
    "Leeds",
    "West Yorkshire"
  ],
  "postalCode": "LS1 6AE",
  "use": "home"
}
],
```

---