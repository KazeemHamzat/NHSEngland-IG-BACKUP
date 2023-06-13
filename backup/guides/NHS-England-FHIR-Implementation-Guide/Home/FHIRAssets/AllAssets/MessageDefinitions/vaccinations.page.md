### vaccinations

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/vaccinations'
select description
```

#### eventCoding

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/vaccinations'
for eventCoding
select system, code, display
```

#### category

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/vaccinations'
select category
```

#### focus

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/vaccinations'
for focus
select code, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ profile + '">'+profile+'</a>', min, max
```