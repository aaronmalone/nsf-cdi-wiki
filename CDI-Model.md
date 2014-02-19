#CID Model

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
  * static
  * date of base simulation [YYYY MM DD]
  * vector of integer

* weekToSimulate
  * static
  * week number to simulate based on startDate
  * integer

* location
  * static
  * State to simulate
  * String (ex. 'OH')  ? or float?

* temperature
  * static
  * Hourly temperature data for week to simulate
  * vector of float

* randomSeed
  * static
  * seed to use for random number generation
  * integer

* price
  * static
  * prices for electricity
  * float vector?

## OUTPUTS
Enter your outputs here.  Make sure to include:
* variable name
* expected size and whether it is dynamic or static
* short description
* type (int, float, string)

## USAGE EXAMPLE
Provide a brief summary of the steps required to run your model and a code example (such as example inputs and expected output).

<br>

##### CID-Specific Question from Aaron:
Where does the **price** data for the CID model come from?