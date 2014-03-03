### About

The simulation function abstraction layer provides a single interface for executing multiple, concurrent calculations on a pool of simulation function processes (SFPs). It handles all of the details of maintaining a network of SFPs (using LAPIS), queuing calculation requests, dispatching calculation requests to individual SFPs, and retrieving results. This allows clients of the simulation function abstraction layer's API to request calculation of simulation function results without worrying about _where_ the calculation will eventually run, _whether resources are currently available_ to run the calculation, and _how to retrieve calculation results_ using LAPIS.

### API

In the initial implementation, the simulation function abstraction layer will allow clients to request calculation execution using an HTTP POST call and receive the result synchronously in the HTTP response.

In a future implementation, clients will be able to request calculations asynchronously.

##### Request body

Clients must specify, in the request body, what values should be used as the inputs to the simulation function. Instead of passing values directly, clients will pass keys into the data-store by which the simulation function abstraction layer will retrieve the values to use. Clients must also pass the keys which the simulation function abstraction layer should use in storing the calculation output values in the database.

An example:

```json
{
  "model" : "cid",
  "timestep" : 7,
  "inputs" : {
    "startDate" : "branch01~subBranch02~startDate~0",
    "location" : "branch01~subBranch02~location~0",
    "temperature" : "branch01~subBranch02~temperature~7",
    "randomSeed" : "branch01~subBranch02~randomSeeForCid~7",
    "weekToSimulate" : "$timestep"
    },
  "outputs":{
    "demand" : "branch01~subBranch02~cidDemand~7"
    }
}
```

Some things to note:
 * Every request will contain the following keys: ```model```, ```timestep```, ```inputs```, and ```outputs```.
   * ```model``` is the name of the simulation function to run. For SFPs connected to the simulation function abstract layer using LAPIS, the value of associated with ```model``` must match the value of a read-only published variable. The name of the published variable has not yet been determined.
   * ```timestep``` is the timestep for the calculation. Every calculation will have a timestep.
   * ```inputs``` maps to a JSON object whose keys are the names of input variables published by the SFP using LAPIS. These are the simulation function inputs. The value associated with each key is a string, and that string is used as a key into the database to retrieve the actual value to pass as an input to the SFP.
   * ```outputs``` maps to a JSON object whose keys are the names of the output variables published by an SFP using LAPIS. These are the simulation function outputs. The value of each key is a string, and that string is used as a key to save the actual output values in the database.
 * The value associated with the ```weekToSimulate``` key in the ```inputs``` object is different from the other values. It is _not_ a string that should be used as a key by which to retrieve the actual input value from the database. Instead, it refers to the timestep value passed in the request. Currently, ```timestep``` will be the only value which can be passed directly in this way.