#RPD Model

## Brief Description
Enter your brief description here

## INPUTS
Enter your inputs here.  Make sure to include:

* variable name
* expected size and whether it is dynamic or static
* short description
* type (int, float, string)

---

* startDate 
  * static size
  * start date of the simulation [YYYY MM DD]
  * vector<integer>
* weekNumber 
  * static size (1)
  * week number from the startDate
  * integer
* temperature
  * static size (?)
  * temperature from the weather model for the week to be simulated
* householdCharacteristics (?)
* occupantCharacteristics (?)


## OUTPUTS
Enter your outputs here.  Make sure to include:
* variable name
* expected size and whether it is dynamic or static
* short description
* type (int, float, string)

---
* BehaviorPatterns
* ApplianceInformation
* demand
  * static size ?
  * residential electricity demand
  * vector of float


### NOTE to Matteo on OUTPUT definitions
You can specify JSON formatted (HashMap) data containers for the variable data such as BehaviorPatterns, etc.  We have added a HashMap datatype to LAPIS to support cases such as this.

## USAGE EXAMPLE
Provide a brief summary of the steps required to run your model and a code example (such as example inputs and expected output).
