## FQL Testing

# Constraints
@```
from StructureDefinition
where type = 'MedicationDispense'
for differential.element
select
id, join constraint { key, severity, human, expression }
```

# Bindings
@```
from StructureDefinition
where type = 'MedicationDispense'
for differential.element
select
id, join binding { strength, valueSet: '{{pagelink:ValueSet-' & valueSet.substring(29) & '}}' }
```

# Extensions
@```
from StructureDefinition
where type = 'MedicationDispense'
for differential.element where differential.element.path.contains('extension:')
select
sliceName, context: path.contains('extension:').replace('.extension', ''), join type { link: '{{pagelink:' & profile.substring(40) & '}}' }
```