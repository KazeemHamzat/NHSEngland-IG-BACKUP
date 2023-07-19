## `Search Parameters`

<b>Definition</b><br>

The following search parameters and search parameter combinations **SHALL** be supported:

- patient:identifier + procedure-code:below

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="15%">Name</th>
     <th data-no-sort width="15%">Type</th>
     <th data-no-sort width="35%">Description</th>
      <th data-no-sort width="15%">Conformance</th>
       <th data-no-sort width="20%">Path</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
date 
    </td>
    <td>
  date
    </td>
     <td>
Vaccination (non-)Administration Date
    </td>
    <td>
SHOULD
    </td>
    <td>
Immunization.date
    </td>
   </tr>    
   <tr>
    <tr>
    <td>
 patient:identifier
    </td>
    <td>
 token
    </td>
     <td>
The patient for the vaccination record
    </td>
    <td>
SHALL
    </td>
    <td>
Immunization.patient
(Patient)
    </td>
   </tr>
    <tr>
    <td>
 procedure-code
    </td>
    <td>
 token
    </td>
     <td>
The target disease and dose number the dose is being administered against
    </td>
    <td>
MAY
    </td>
    <td>
Immunization.extension:vaccinationProcedure
    </td>
   </tr>    
    <tr>
    <td>
 status
    </td>
    <td>
 token
    </td>
     <td>
Immunization event status
    </td>
    <td>
MAY
    </td>
    <td>
Immunization.status
    </td>
   </tr>  
   </tbody>
</table>

---