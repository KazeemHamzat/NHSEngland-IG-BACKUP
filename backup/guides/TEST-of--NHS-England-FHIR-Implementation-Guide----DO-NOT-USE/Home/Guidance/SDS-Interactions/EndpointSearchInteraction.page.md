### Endpoint Search Interactions

The SCR API SHALL support a search interaction to return Endpoint resources using search parameters for:
- [Mandatory] Organisation code - ODS code of the target organisation (i.e. GP practice exposing the endpoint)
- [Mandatory] MHS Interaction ID - type of Interaction supported by Endpoint

Endpoint resources are returned as a searchset Bundle containing 0, 1 or many matching Endpoint resources

The Endpoint Search Interaction supports GP Connect use cases by allowing a consumer system to retrieve the Message Handling System (MHS) record for a capability at a target GP provider organisation

### Search Parameter

| Data Item          | Query Parameter  | Query Target                              | Example                       |
|--
| Organisation code  | organization     | managingOrganization                      | organization=[targetODSCode]  |
| MHS Interaction ID | identifier       | Endpoint.identifier:NhsEndpointServiceId  | identifier=https://fhir.nhs.uk/Id/nhsEndpointServiceId\|\[interactionId] |

#### Request pattern

```
GET [baseURL]/Endpoint?
  organization=[ODSNamingSystem]|[targetODSCode]&
  identifier=[EndpointServiceIdNamingSystem]|[interactionId]
```

#### Example request
```
GET [baseURL]/Endpoint?
  organization=https://fhir.nhs.uk/Id/ods-organization-code|R8008&
  identifier=https://fhir.nhs.uk/Id/nhsEndpointServiceId|urn:nhs:names:services:psis:REPC_IN150016UK05
```

#### Example response payload

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
  {{xml:bbea6247-6d81-4d92-b2c0-8779aacdb838-duplicate-2}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
  {{json:bbea6247-6d81-4d92-b2c0-8779aacdb838-duplicate-2}}
</div>

