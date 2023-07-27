### Endpoint Data Mapping

This table specifies the mapping from data requirements, Message Handling System (MHS) record, to FHIR targets within the SDS-Endpoint resource

| Data Item             | LDAP Attribute                | Cardinality |  FHIR Target                                                                            |
|--
| Organisation Code     | nhsIdCode                     | 1     | Endpoint.managingOrganization                                                                 |
| Service-Interaction   | nhsMhsSvcIA                   | 1     | Endpoint.identifier:NhsEndpointServiceId                                                      |
| FQDN of MHS           | nhsMHSFQDN                    | 1     | Endpoint.identifier:NhsMhsFQDN                                                                |
| End Point             | nhsMhsEndPoint                | 1     | Endpoint.address                                                                              |
| Party Key             | nhsMhsPartyKey                | 1     | Endpoint.identifier:NhsMhsPartyKey                                                            |
| CPA Identifier        | nhsMhsCPAId                   | 1     | Endpoint.identifier:NhsMhsCPAId                                                               |
| MHS Identifier        | uniqueIdentifier              | 1     | Endpoint.identifier:NhsSpineASID                                                              |
| Sync Reply Mode       | nhsMhsSyncReplyMode           | 0..1  | Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSSyncReplyMode         |
| Retry Interval        | nhsMhsRetryInterval           | 0..1  | Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSRetryInterval         |
| Retries               | nhsMhsRetries                 | 0..1  | Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSRetries               |
| Persist duration      | nhsMhsPersistduration         | 0..1  | Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSPersistDuration       |
| Duplicate Elimination | nhsMhsDuplicateElimination    | 0..1  | Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSDuplicateElimination  |
| Ack Requested         | nhsMhsAckRequested            | 0..1  | Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSAckRequested          |
| Actor         | nhsMhsActor            | 0..1  | Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSActor          |