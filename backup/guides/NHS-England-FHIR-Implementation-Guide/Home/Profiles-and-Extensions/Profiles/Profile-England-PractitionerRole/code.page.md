## `code`

<b>Definition:</b>

Only supply if this is known from SmartCard/CIS2 data.

```json
"code":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/NHSDigital-SDS-JobRoleCode",
                    "code": "S0030:G0100:R0620"
                  }
            ]
        }
    ],
```


The previous system for this entry was `https://fhir.hl7org.uk/CodeSystem/UKCore-SDSJobRoleName`, this has been retired and `https://fhir.nhs.uk/CodeSystem/England-SDS-JobRoleCode` should be used instead. Note: `https://fhir.hl7org.uk/CodeSystem/UKCore-SDSJobRoleName` is currently used by EPS but will be retired in a future release. Pending further guidance, both CodeSystems should be used for EPS interations


### `code.coding:sdsJobRoleCode`

This value should be sourced from either APIM OAuth2 userinfo endpoint, SDS LDAP or CIS2/SmartCard details.

The CodeSystem is variable and is not present in this Implementation Guide.


---

