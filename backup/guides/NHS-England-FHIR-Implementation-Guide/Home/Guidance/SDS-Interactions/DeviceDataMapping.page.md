### Device Data Mapping

This table specifies the mapping from data requirements, Accredited System record, to FHIR targets within the SDS-Device resource

| Data Item                      | LDAP Attribute   | Cardinality |  FHIR Target    | Notes       |
|--------------------------------|------------------|-------------|-----------------|-------------|
| Accredited System Identifier   | uniqueIdentifier | 1           | Device.identifier:NhsSpineASID                                  | |
| Managing Organisation Code     | nhsIdCode        | 1           | Device.extension:managingOrganisation (for GP System supplier)  | |
| Client Code                    | nhsAsClient      | 0..*        | Device.owner (for GP System i.e. GP Practice)                   | List of Organisation or Site codes, or Organisational Work Groups which use this Accredited System. Though the cardinality is set to 0..*, EPR application ensures there is 1 value in this attribute. |
| Party Key                      | nhsMhsPartyKey   | 1           | Device.identifier:NhsMhsPartyKey                                | |
| Service-Interactions           | nhsAsSvcIA       | 1..*        | Device.identifier:NhsEndpointServiceId                          | |
| ACF Characteristics            | nhsAsACF         | 0..*        | not mapped - not returned   | |
| Description                    | description      | 0..1        | not mapped - not returned   | |
| Category Bag                   | nhsAsCategoryBag | 0..*        | not mapped - not returned   | |
| Product                        | nhsProductKey    | 1           | not mapped - not returned   | |
| Requestor’s Identity           | nhsRequestorURP  | 1           | not mapped - not returned   | |
| Date Requested                 | nhsDateRequested | 1           | not mapped - not returned   | |
| Approver’s Identity            | nhsApproverURP   | 1           | not mapped - not returned   | |
| Date Approved                  | nhsDateApproved  | 1           | not mapped - not returned   | |

`not mapped - not returned` - these data items in the AccreditedSystem record are not returned by the Device endpoint and so are not mapped to a FHIR Target