### Device Search Interactions

The SCR API SHALL support a search interaction to return Device resources using search parameters for:
- [Mandatory] Organisation code - ODS code of the target organisation (i.e. GP practice operating the software instance)
- [Mandatory] MHS Interaction ID - type of Interaction supported by software instance
- [Optional ] Manufacturer's organisation code - ODS code of the manufacturer's organisation (i.e. GP System supplier)
- [Optional ] Party Key - identifier representing the target organisation and service interaction

Device resources are returned as a searchset Bundle containing 0, 1 or many matching Endpoint resources

{{pagelink:SearchParameter-SDS-ManagingOrganisation}} has been defined to specify search on the managingOrganisation extension

The Device Search Interaction supports GP Connect use cases by allowing a consumer system to retrieve the Accredited System (AS) record for a capability at a target GP provider organisation OR at their own organisation

### Search Parameter

<table class="regular assets">
<thead>
<tr>
<th>Data Item</th>
<th>Query Parameter</th>
<th>Query Target</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td>Organisation code</td>
<td>organization</td>
<td>Device.owner</td>
<td>organization=[GPSystemODSCode]</td>
</tr>
<tr>
<td>MHS Interaction ID</td>
<td>identifier</td>
<td>Device.identifier:NhsEndpointServiceId</td>
<td>identifier=https://fhir.nhs.uk/Id/nhsEndpointServiceId|[interactionId]</td>
</tr>
<tr>
<td>Manufacturer organisation code</td>
<td>managing-organisation</td>
<td>Device.extension:Extension-SDS-ManagingOrganisation</td>
<td>managing-organisation=[supplierODSCode]</td>
</tr>
<tr>
<td>Party Key</td>
<td>identifier</td>
<td>Device.identifier:NhsMhsPartyKey</td>
<td>identifier=https://fhir.nhs.uk/Id/nhsMhsPartyKey|[partyKey]</td>
</tr>
</tbody>
</table>

#### Request pattern

```
GET [baseURL]/Device?
  organization=[ODSNamingSystem]|[GPSystemODSCode]&
  identifier=[EndpointServiceIdNamingSystem]|[interactionId]&
  managing-organisation=[ODSNamingSystem]|[supplierODSCode]&
  identifier=[PartyKeyNamingSystem]|[partyKey]
```

#### Example request
```
GET [baseURL]/Device?
  organization=https://fhir.nhs.uk/Id/ods-organization-code|R8008&
  identifier=https://fhir.nhs.uk/Id/nhsEndpointServiceId|urn:nhs:names:services:psis:REPC_IN150016UK05&
  managing-organisation=https://fhir.nhs.uk/Id/ods-organization-code|T10101&
  identifier=https://fhir.nhs.uk/Id/nhsMhsPartyKey|R8008-0000806
```

#### Example response payload

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
  {{xml:6cf80168-a1ef-49a2-bb92-e870c8e11e3c-duplicate-2}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
  {{json:6cf80168-a1ef-49a2-bb92-e870c8e11e3c-duplicate-2}}
</div>

