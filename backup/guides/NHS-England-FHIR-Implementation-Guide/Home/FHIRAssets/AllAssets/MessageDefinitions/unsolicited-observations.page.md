### unsolicited-observations

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/unsolicited-observations'
select description
```

#### eventCoding

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/unsolicited-observations'
for eventCoding
select system, code, display
```

#### category

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/unsolicited-observations'
select category
```

#### focus

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/unsolicited-observations'
for focus
select code, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ profile + '">'+profile+'</a>', min, max
```

### Examples 

- Observations with patient referenced by NHS Number (no Patient resource) {{link:d0cf7825-1576-419b-8cbd-88db3ea1c70c}}