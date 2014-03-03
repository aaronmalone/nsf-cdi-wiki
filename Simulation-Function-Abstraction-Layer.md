### About

The simulation function abstraction layer provides a single interface for executing multiple, concurrent calculations on a pool of simulation function processes (SFPs). It handles all of the details of maintaining a network of SFPs (using LAPIS), queuing calculation requests, dispatching calculation requests to individual SFPs, and retrieving results. This allows clients of the simulation function abstraction layer's API to request calculation of simulation function results without worrying about _where_ the calculation will eventually run, _whether resources are currently available_ to run the calculation, and _how to retrieve calculation results_ using LAPIS.

### API

In the initial implementation, the simulation function abstraction layer will allow clients to request calculation execution using an HTTP POST call and receive the result synchronously in the HTTP response.

In a future implementation, clients will be able to request calculations asynchronously.

##### Request body

Clients must specify, in the request body, what values should be used as the inputs to the simulation function. Instead of passing values directly, clients will pass keys into the data-store by which the simulation function abstraction layer will retrieve the values to use. Clients must also pass the keys which the simulation function abstraction layer should use in storing the calculation output values in the database.

```json
{
  "model":"base-weather",
  "inputs":{
    "":""}
  "outputs":{
    }
  
}
```

TODO: finish the weather model example
