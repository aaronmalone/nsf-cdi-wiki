#SUCM Model

## Brief Description
Enter your brief description here

## INPUTS
Enter your inputs here.  Make sure to include:
* variable name
* expected size and whether it is dynamic or static
* short description
* type (int, float, string)

---
* temperature
  * static size (?)
  * temperature from the weather model for the week to be simulated
  * float vector
* wind
  * static size (?)
  * wind from the weather model for the week to be simulated
  * float vector
* solar
  * static size (?)
  * solar from the weather model for the week to be simulated
  * float vector
* CIDDemand
  * static size (?)
  * electricity demand from CID model
  * float vector
* RDODemand
  * static size (?)
  * electricity demand from RDO model
  * float vector
* Generation(?)
* Cost (?)
* Constraints (?)

## OUTPUTS
Enter your inputs here.  Make sure to include:
* variable name
* expected size and whether it is dynamic or static
* short description
* type (int, float, string)

---

* Generation by plant(?)
* Plant Online (?)
* Price per generation unit (?)

### NOTE to AMY on OUTPUT definitions
You can specify JSON formatted (HashMap) data containers for the variable data such as plant generation, etc.  We have added a HashMap datatype to LAPIS to support cases such as this.

## USAGE EXAMPLE
Provide a brief summary of the steps required to run your model and a code example (such as example inputs and expected output).
