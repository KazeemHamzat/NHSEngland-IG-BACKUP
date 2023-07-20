## `destination`

<b>Definition</b><br>

Lists all the destinations where message is be delivered to. 

The recipient of a message takes the responsibility of delivering to all the `destination.endpoint`s. Similarly the sender **MUST NOT** include destination's the recipient can not deliver to, these destinations **MUST** be removed from the message. Additional rules for endpoint can be found in the source section below.

 #### Requirements

 Indicates where message is to be sent for routing purposes.  Allows verification of "am I the intended recipient".

```json
"destination": [
                    {
                        "endpoint": "urn:nhs-uk:addressing:mesh:Y90638OT002",
                        "receiver": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                                "value": "Y9063"
                            }
                        }
                    }
                ]
```

 #### Comment

 There SHOULD be at least one destination, but in some circumstances, the source system is unaware of any particular destination system.

 ---