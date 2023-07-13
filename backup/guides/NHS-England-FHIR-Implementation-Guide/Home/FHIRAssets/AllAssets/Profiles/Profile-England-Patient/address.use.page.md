## `address.use`

<b>Definition:</b>

Purpose of this address:

- home - the home address is the patient's normal residence. Home address is also known as usual, main, registered, current or permanent address
- temp - a temporary address is an address used for a set period of time, but where the patient's home, permanent address remains unchanged
- billing - an address used for correspondence purposes only
- work - an office address. This can be returned due to legacy data but cannot be added or replaced on update

A patient should have no more than one current temp and/or billing address. However, historically this was constrained only by the integration requirements and was not enforced so theoretically more than one can exist for a patient when retrieving. Where multiple instances already exist for the patient it is not expected that local systems should manage those, but should choose the most appropriate one to maintain (e.g. by examining period dates).

A home address is the patient's main residential address and should normally be used for all clinical and demographic purposes, including clinical and appointment correspondence. However additionally, temp and billing addresses may be provided by a patient when there is a requirement to record an alternative location for the purposes of unbroken care. When sending correspondence to a patient:

- a present and valid billing address may take precedence over home and temp addresses. A patient should have only a single current billing address. An address is considered 'valid' according to its period start and end dates.
- if no current billing address is provided, a temp address may take precedence over the home address, again if it is valid according to its period start and end dates.
- if there is no valid, current billing and/or temp address, the home address must be used.

---