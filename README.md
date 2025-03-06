# Practical Linear Regression

## Dataset

The [automobile miles per gallon (auto-mpg)](https://archive.ics.uci.edu/dataset/9/auto+mpg) dataset was originally published as a standard dataset in the statlib library.
The data as sourced from the UCI ML Library is in the `.data` format which is a fixed width data format (yup, it's that old). The dataset as provided has no columnar metadata, in other words, it has no column names or datatypes in the data itself. Further, the UCI source does not provide the original units of the data 🤦. However, with some digging and assumptions in using the imperial scale (I assume these are imperial given that we are talking about 'miles' and 'gallons') here is an outline of the values

| Variable     | Description                                                                                                                                                      | Unit                  |
|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|
| displacement | Engine displacement is the measure of the cylinder volume swept by all of the pistons of a piston engine, excluding the combustion chambers.                    | cubic inches         |
| mpg         | The number of miles that a vehicle can travel on 1 gallon of fuel, assuming no load. This dataset quotes 'city-cycle' mpg which is a measure for driving in urban areas.                                                                             | miles/gallon         |
| cylinders   | The number of cylinders in a vehicle's engine. Cylinders comprise a piston and two valves (inflow and outflow) and are located within the engine.                | integer              |
| horsepower  | A unit of measurement of power, or the rate at which work is done, usually in reference to the output of engines or motors.                                      | hp (imperial)        |
| weight      | The relative mass of the vehicle.                                                                                                                                | pounds               |
| acceleration| The time taken for a vehicle to cover a quarter of a mile from an idle state.                                                                                   | seconds           |
| model_year  | The year in which the vehicle model was produced.                                                                                                               | years (e.g., 70 = 1970) |
| origin      | No idea what this is... Could be the origin of the vehicle, but I don't know what an origin of 1 means... Sorry.                                                | 🤷                   |

