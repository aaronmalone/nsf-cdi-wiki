#TEC Model

## Brief Description
Enter your brief description here

## INPUTS
Enter your inputs here.  Make sure to include:
* variable name
* expected size and whether it is dynamic or static
* short description
* type (int, float, string)

---
* driverBehaviorPattern (?)
* commuteDistanceToWork
  * static
  * commute distance to work for driver
  * float vector
* vehicleCharacteristics (?)
* randomSeed
  * static
  * seed to use to generate random numbers
  * static integer

## OUTPUTS
Enter your outputs here.  Make sure to include:
* variable name
* expected size and whether it is dynamic or static
* short description
* type (int, float, string)

---

* consumption
  * static (3x1008)
  * energy consumption of vehicle 
  * float matrix
* distanceDriven 
  * static (1x1008)
  * distance driven by vehicle
  * float vector
* tripsFailed
  * static (1x1008)
  * number of trips failed due to energy running out
  * float vector

### NOTE to Matteo on OUTPUT definitions
You can specify JSON formatted (HashMap) data containers for the variable data such as plant generation, etc.  We have added a HashMap datatype to LAPIS to support cases such as this.

## USAGE EXAMPLE
Provide a brief summary of the steps required to run your model and a code example (such as example inputs and expected output).
