### Device Data Mapping

This table specifies the mapping from data requirements, Accredited System record, to FHIR targets within the SDS-Device resource

<table class="regular assets">
<thead>
<tr>
<th>Data Item</th>
<th>LDAP Attribute</th>
<th>Cardinality</th>
<th>FHIR Target</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr>
<td>Accredited System Identifier</td>
<td>uniqueIdentifier</td>
<td>1</td>
<td>Device.identifier:NhsSpineASID</td>
<td></td>
</tr>
<tr>
<td>Managing Organisation Code</td>
<td>nhsIdCode</td>
<td>1</td>
<td>Device.extension:managingOrganisation (for GP System supplier)</td>
<td></td>
</tr>
<tr>
<td>Client Code</td>
<td>nhsAsClient</td>
<td>0..*</td>
<td>Device.owner (for GP System i.e. GP Practice)</td>
<td>List of Organisation or Site codes, or Organisational Work Groups which use this Accredited System. Though the cardinality is set to 0..*, EPR application ensures there is 1 value in this attribute.</td>
</tr>
<tr>
<td>Party Key</td>
<td>nhsMhsPartyKey</td>
<td>1</td>
<td>Device.identifier:NhsMhsPartyKey</td>
<td></td>
</tr>
<tr>
<td>Service-Interactions</td>
<td>nhsAsSvcIA</td>
<td>1..*</td>
<td>Device.identifier:NhsEndpointServiceId</td>
<td></td>
</tr>
<tr>
<td>ACF Characteristics</td>
<td>nhsAsACF</td>
<td>0..*</td>
<td>not mapped - not returned</td>
<td></td>
</tr>
<tr>
<td>Description</td>
<td>description</td>
<td>0..1</td>
<td>not mapped - not returned</td>
<td></td>
</tr>
<tr>
<td>Category Bag</td>
<td>nhsAsCategoryBag</td>
<td>0..*</td>
<td>not mapped - not returned</td>
<td></td>
</tr>
<tr>
<td>Product</td>
<td>nhsProductKey</td>
<td>1</td>
<td>not mapped - not returned</td>
<td></td>
</tr>
<tr>
<td>Requestor’s Identity</td>
<td>nhsRequestorURP</td>
<td>1</td>
<td>not mapped - not returned</td>
<td></td>
</tr>
<tr>
<td>Date Requested</td>
<td>nhsDateRequested</td>
<td>1</td>
<td>not mapped - not returned</td>
<td></td>
</tr>
<tr>
<td>Approver’s Identity</td>
<td>nhsApproverURP</td>
<td>1</td>
<td>not mapped - not returned</td>
<td></td>
</tr>
<tr>
<td>Date Approved</td>
<td>nhsDateApproved</td>
<td>1</td>
<td>not mapped - not returned</td>
<td></td>
</tr>
</tbody>
</table>

`not mapped - not returned` - these data items in the AccreditedSystem record are not returned by the Device endpoint and so are not mapped to a FHIR Target