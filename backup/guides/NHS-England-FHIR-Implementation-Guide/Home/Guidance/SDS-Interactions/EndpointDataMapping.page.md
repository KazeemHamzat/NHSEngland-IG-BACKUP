### Endpoint Data Mapping

This table specifies the mapping from data requirements, Message Handling System (MHS) record, to FHIR targets within the SDS-Endpoint resource

<table class="regular assets">
<thead>
<tr>
<th>Data Item</th>
<th>LDAP Attribute</th>
<th>Cardinality</th>
<th>FHIR Target</th>
</tr>
</thead>
<tbody>
<tr>
<td>Organisation Code</td>
<td>nhsIdCode</td>
<td>1</td>
<td>Endpoint.managingOrganization</td>
</tr>
<tr>
<td>Service-Interaction</td>
<td>nhsMhsSvcIA</td>
<td>1</td>
<td>Endpoint.identifier:NhsEndpointServiceId</td>
</tr>
<tr>
<td>FQDN of MHS</td>
<td>nhsMHSFQDN</td>
<td>1</td>
<td>Endpoint.identifier:NhsMhsFQDN</td>
</tr>
<tr>
<td>End Point</td>
<td>nhsMhsEndPoint</td>
<td>1</td>
<td>Endpoint.address</td>
</tr>
<tr>
<td>Party Key</td>
<td>nhsMhsPartyKey</td>
<td>1</td>
<td>Endpoint.identifier:NhsMhsPartyKey</td>
</tr>
<tr>
<td>CPA Identifier</td>
<td>nhsMhsCPAId</td>
<td>1</td>
<td>Endpoint.identifier:NhsMhsCPAId</td>
</tr>
<tr>
<td>MHS Identifier</td>
<td>uniqueIdentifier</td>
<td>1</td>
<td>Endpoint.identifier:NhsSpineASID</td>
</tr>
<tr>
<td>Sync Reply Mode</td>
<td>nhsMhsSyncReplyMode</td>
<td>0..1</td>
<td>Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSSyncReplyMode</td>
</tr>
<tr>
<td>Retry Interval</td>
<td>nhsMhsRetryInterval</td>
<td>0..1</td>
<td>Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSRetryInterval</td>
</tr>
<tr>
<td>Retries</td>
<td>nhsMhsRetries</td>
<td>0..1</td>
<td>Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSRetries</td>
</tr>
<tr>
<td>Persist duration</td>
<td>nhsMhsPersistduration</td>
<td>0..1</td>
<td>Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSPersistDuration</td>
</tr>
<tr>
<td>Duplicate Elimination</td>
<td>nhsMhsDuplicateElimination</td>
<td>0..1</td>
<td>Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSDuplicateElimination</td>
</tr>
<tr>
<td>Ack Requested</td>
<td>nhsMhsAckRequested</td>
<td>0..1</td>
<td>Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSAckRequested</td>
</tr>
<tr>
<td>Actor</td>
<td>nhsMhsActor</td>
<td>0..1</td>
<td>Endpoint.extension:ExtensionSDSReliabilityConfiguration.extension:nhsMHSActor</td>
</tr>
</tbody>
</table>