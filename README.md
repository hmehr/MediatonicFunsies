# MediatonicFunsies
The demo application dedicated to Mediatonic tech guys!

## Requirements
* Docker is needed to spin up Redis
* [Dotnet core runtime 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* Visual Studio ideally to debug
* An HTTP client to send requests to the application for testing purposes. I use [postman](https://www.postman.com/) and I have shared my collection [here](https://www.getpostman.com/collections/978d8fbd71c29e9a0e53).

## Assumptions
* Each person can have 0 or more animals. An animal doesn't exist without a person.
* Each animal can have 0 or more metrics. A metric doesn't exist without an animal.
* Each metric can have 0 or more modifiers. A modifer doesnt' exist without a metric.
* The metrics are a function of time calculated by multiplying elapsed time in the life of the animal and the rate of metric increase/decrease. The initial value for each metric is taken into account.
* The rate of a metrics increase/decrease is linear
* Petting or feeding animals are modifiers that are a percentage of the metrics at that point in time with a one time effect.


## How to run/debug
* To run the appication go to the root folder of the application and do a `docker-compose build` followed by `docker-compose up`
* To debug the application, Redis needs to be up and running. If `docker-compose up` is still running, then the application can just be run in debug mode and it should work
* Please note that the host URL for debug mode is `http://localhost:5000` and for the run mode is `http://localhost:8081`

## Missing work
Due to time constraint, I obviously couldn't do everything I'd have liked to do. I'd have liked to:
* Add more unit tests, and ideally some end-to-end test
* More validations for the inputs
* The metric object should not save the `value` in Redis. It could be improved where two separate objects can be used for saving into Redis and the response sent back to the client.
* More comments
