## {{page-title}}

The NHS England IG uses Simplifier NPM packages to release the FHIR Conformance Assets.

The NHSE Packages are located with the <a href="https://simplifier.net/NHS-England-Implementation-Guide/~packages">Project Packages area.</a>

<a href="https://docs.simplifier.net/projects/Firely-Terminal/Managing-Packages.html?highlight=simplifier%20packages">Further information on Packages is available in the Simplifier documentation.</a>

These packages may be used to validate conformance of an implementation of FHIR against a particular version or versions of the NHS England IG. 

The Simplifier NPM pages are released as part of a NHS England release and normally coincides with an Implementation Guide release. The NPM package name format is all lower case and as described below:

fhir.[fhir version]nhsengland.[sequence release] [major].[minor].[patch]

where

- <code><i>[fhir version]</i></code> - The release version of FHIR used with the NHS England (currently R4).
- <code><i>[sequence release]</i></code> - The sequence and release (currently stu1).
- <code><i>[major]</i></code> - The major release aligns with the Implementation Guide major version.
- <code><i>[minor]</i></code> - The minor version aligns with the Implementation Guide minor version.
- <code><i>[patch]</i></code> - The patch version starts at 0 and increments by 1 for every package release for a particular Implementation Release. Note: a Implementation guide may have more than one package associated with it.

### Package example

For example 'fhir.r4.nhsengland.stu1 0.1.0`


---

<!--Original
The Simplifier NPM packages are released as part of a UK Core release, normally contaning an Implementation Guide and a NPM Package. The NPM package is named based on a seven-item string (1_2_3_4_5_6_7) which is described below:

`fhir`_"fhir version"_`ukcore`_"sequence_release"_"major version"_"minor version"_patch version"`

<ol>
<li>A fixed value <code>fhir</code></li>
<li>The release version of FHIR used with the UK Core (currently R4)</li>
<li>A fixed value <code>ukcore</code></li>
<li>The sequence and release (currently stu1)
<li>The major release aligns with the Implementation Guide major version and always 0 unless the release has been though a ballot</li>
<li>The minor version aligns with the Implementation Guide minor version</li>
<li>The patch version starts at 0 and increments by 1 for every package release for a particular Implementation Release. Note: a Implementation guide may have more than one package associated with it.
</ol>

### Package example

For example `fhir.r4.ukcore.stu1 0.1.0`
 -->
