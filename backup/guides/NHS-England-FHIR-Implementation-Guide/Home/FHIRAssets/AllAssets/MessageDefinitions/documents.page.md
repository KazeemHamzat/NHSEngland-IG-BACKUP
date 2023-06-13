## {{page-title}}

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/document'
select description
```

#### eventCoding

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/document'
for eventCoding
select system, code, display
```

#### category

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/document'
select category
```

#### focus

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/document'
for focus
select code, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ profile + '">'+profile+'</a>', min, max
```

### Examples 

- Document with patient referenced by NHS Number (no Patient resource) {{link:d12dc439-ca5c-4177-bb70-4fece88edab0-duplicate-2}}
- Document with Patient resource {{link:Bundle-Bundle-message-document}}
