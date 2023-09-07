## {{page-title}}

Each example SHOULD have the minimum amount of information necessary to convey the intended message whilst ensuring it is still a valid resource or extension. If there any agreed Clinical scenario(s), then these SHALL be represented  examples.

### Resource Example
Each Resource example SHALL include the following within the Implementation Guide, along with any mandatory elements and any elements listed with the Profiles to illustrate the constraints on NHS England IG than the resource applies:

``` xml
<[Resource] xmlns="http://hl7.org/fhir">
    <id value="[ResourceExampleName]" />
    [Elements to convey resource example & any other elements to create a valid example]
</[Resource]> 
```

### Extension Example
Each Extension Example SHALL have the following, along with any mandatory elements:
``` xml
<[Resource] xmlns="http://hl7.org/fhir">
    <id value="[ResourceExampleName]" />
     <extension url="[ExtensionUrl]">
    [Elements to convey Extension example & any other elements to create a valid example]
</[Resource]> 
```

### Meta Element

The <code>Resource.meta</code> element SHALL NOT be used for Examples.

---

