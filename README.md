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

## Predicted Horsepower Results

The following car models are missing values for horsepower in the dataset, I did my best to lookup the actual horsepower values to check how well our model did... and just for fun.


| Car Name                 | Model Year | Cylinders | Predicted Horsepower | Actual Horsepower | Source |
|--------------------------|------------|-----------|----------------------|-------------------|------------------------------------------------------------------------------------------------|
| Ford Pinto               | 1971       | 4         | 75.0                 | 75                | [Auto Evoution](https://www.autoevolution.com/cars/ford-pinto-1971.html#aeng_ford-pinto-1971-16) |
| Ford Maverick            | 1974       | 6         | 94.5                | 82                | [Vega Dataset (GitHub)](https://github.com/vega/vega/blob/main/docs/data/cars.json) |
| Renault LeCar Deluxe     | 1980       | 4         | 60.7                 | 55                | [Vega Dataset (GitHub)](https://github.com/vega/vega/blob/main/docs/data/cars.json) |
| Ford Mustang Cobra       | 1980       | 4         | 95.5                 | 88                | [Vega Dataset (GitHub)](https://github.com/vega/vega/blob/main/docs/data/cars.json) |
| Renault 18i              | 1981       | 4         | 74.0                 | 81                | [Vega Dataset (GitHub)](https://github.com/vega/vega/blob/main/docs/data/cars.json) |
| AMC Concord DL           | 1982       | 4         | 76                 | 110                | [Wikipedia](https://en.wikipedia.org/wiki/AMC_Concord) |