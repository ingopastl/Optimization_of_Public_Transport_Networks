
# Optimization of Public Transport Networks by Considering Alternative Positions for Network Stations

This is the source code used on the paper called, "Optimization of Public Transport Networks by Considering Alternative Positions for Network Stations", written by Ingo Porfírio Pastl Montarroyos and Danilo Ricardo Barbosa de Araújo.
## Paper abstract
Nowadays, the planning of metropolitan areas considers improving the quality of life of inhabitants and urban mobility is one of the main concerns. Studies point out that investments in public transportation and other modes are aimed at the overall improvement of mobility. However, there is a gap in proper tools for optimizing public transport networks. In fact, network optimization is an NP-Hard problem and there are usually many conflicting objectives that need to be optimized simultaneously. This paper proposes the use of many-objective evolutionary algorithms to address the problem of public transport networks optimization, focusing on metropolitan bus lines. The proposal consists in optimizing the position of bus stops and consequently obtaining new routes that pass through these stops in order to minimize the average travel time, the time spent between origin / destination and the variance of distance between the stops. To evaluate our proposal, a simulator was used to simulate the behavior of different passenger profiles in an urban area and the results were compared between the lines obtained by the optimization process and existing bus lines in the city of São Paulo. According to our results, optimized bus routes have mean travel time 22% less than the existing route and the time spent between origin/destination has decreased up to 18%.
## Get it running

The project uses Maven to manage Java references and the JMetal Java framework to handle the optimization process.

To get it running you should first set up a server with the open source [OSRM routing engine]([https://linktodocumentation](https://project-osrm.org/)).

After that you should change the hardcoded value of the OWNSERVER variable in the follwing .java file: 

```url
  src/main/java/services/osrm/OsrmAPIRequester.java
```

The new value should be the URL exposed by your OSRM HTTP server.

## File tree description
```
|   jMetal.log - JMetal framework log file.
|   pom.xml - Maven file.
|   PTD_Public_Transport.iml - Maven file.
|
+---src
|   \---main
|       +---java
|       |   |   Main.java - Main class that is going to run the algorithm.
|       |   |
|       |   +---beans
|       |   |       BusLine.java - Bean data class.
|       |   |       BusStop.java - Bean data class.
|       |   |       BusStopRelation.java - Bean data class.
|       |   |       Itinerary.java - Bean data class.
|       |   |
|       |   +---jmetal
|       |   |       Hypervolume.java - JMetal class that implements the hypervolume indicator.
|       |   |       NSGAIII.java - JMetal NSGAIII algorithm class.
|       |   |       NSGAIIIBuilder.java - JMetal builder class for the NSGAIII algorithm.
|       |   |       PTDJMetalProblem.java - JMetal problem class.
|       |   |       PublicTransportNetworkCrossover.java - JMetal crossover class.
|       |   |       PublicTransportNetworkMutation.java - JMetal mutation class.
|       |   |       ReferenceParetoFrontGenerator.java - JMetal reference pareto front generator.
|       |   |
|       |   +---repositories
|       |   |       BusLineRepository.java - Repository class which holds data about bus lines.
|       |   |       BusStopRelationRepository.java - Repository class which holds data about bus stop relations.
|       |   |       BusStopRepository.java - Repository class which holds data about bus stops.
|       |   |       ItineraryRepository.java - Repository class which holds data about itineraries.
|       |   |
|       |   \---services
|       |       |   APIRequester.java - Base API requester class that is extended by the OsrmAPIRequester class.
|       |       |   HttpManager.java - HTTP manager used by the simulator.
|       |       |   TripSimulator.java - Base simulator class that is extended by the OsrmTripSimulator class.
|       |       |
|       |       \---osrm
|       |               OsrmAPIRequester.java - Class used to call the OSRM HTTP API.
|       |               OsrmTripSimulator.java - Simulator that uses the OSRM HTTP API to simulate bus and walking routes.
|       |
|       \---resources
|           \---busData - Folder containing the public transport data used in the project.
```
