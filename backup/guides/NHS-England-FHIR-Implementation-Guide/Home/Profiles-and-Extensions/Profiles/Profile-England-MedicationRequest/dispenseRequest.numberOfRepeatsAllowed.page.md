## `dispenseRequest.numberOfRepeatsAllowed`

<b>Definition</b><br>

An integer indicating the number of times, in addition to the original dispense, (aka refills or repeats) that the patient can receive the prescribed medication. Usage Notes: This integer does not include the original order dispense. This means that if an order indicates dispense 30 tablets plus &;3 repeats&;, then the order can be dispensed a total of 4 times and the patient can receive a total of 120 tablets. A prescriber may explicitly say that zero refills are permitted after the initial dispense.
    
The number of repeat issues authorised if specified. 

**MUST** be present where a `continuous` or `continuous-repeat-dispensing` is authorised for a defined number of issues.

**MUST** NOT be specified where the number of repeat issues has not been defined. Therefore, the numberOfRepeats allowed is the total number of allowed issues. See also extension repeatInformation.

For `continuous` orders and `continuous-repeat-dispensing` with intent=`reflex-order` (i.e., orders sent from EPS to pharmacists) this &lt;b&gt;MUST&lt;/b&gt; be zero. The `numberOfRepeatsAllowed` in the extension to `basedOn` can be used to convey this information to inform patients that they need to re-order the medication. 

Example for a `continuous` issue:

<br>

 ```json 
"dispenseRequest": {
        "numberOfRepeatsAllowed": 0
    }
```

Example for a `continuous-repeat-dispensing` issue with intent of `original-order`: 

 <br>

 ```json 
"dispenseRequest": {
        "numberOfRepeatsAllowed": 2
    }
```
 This will result in a total of three issues of the medication.

---
  