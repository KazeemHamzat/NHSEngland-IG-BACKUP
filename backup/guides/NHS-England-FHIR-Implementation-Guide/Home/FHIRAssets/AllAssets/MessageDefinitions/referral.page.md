### referral

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/referral'
select description
```

#### eventCoding

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/referral'
for eventCoding
select system, code, display
```

#### category

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/referral'
select category
```

#### focus

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/referral'
for focus
select code, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ profile + '">'+profile+'</a>', min, max
```