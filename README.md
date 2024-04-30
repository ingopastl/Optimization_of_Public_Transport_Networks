
# Optimization of Public Transport Networks by Considering Alternative Positions for Network Stations

This is the source code used on the paper called, "Optimization of Public Transport Networks by Considering Alternative Positions for Network Stations", written by Ingo Porfírio Pastl Montarroyos and Danilo Ricardo Barbosa de Araújo.
## Paper abstract
Nowadays, the planning of metropolitan areas considers improving the quality of life of inhabitants and urban mobility is one of the main concerns. Studies point out that investments in public transportation and other modes are aimed at the overall improvement of mobility. However, there is a gap in proper tools for optimizing public transport networks. In fact, network optimization is an NP-Hard problem and there are usually many conflicting objectives that need to be optimized simultaneously. This paper proposes the use of manyobjective evolutionary algorithms to address the problem of public transport networks optimization, focusing on metropolitan bus lines. The proposal consists in optimizing the position of bus stops and consequently obtaining new routes that pass through these stops in order to minimize the average travel time, the time spent between origin / destination and the variance of distance between the stops. To evaluate our proposal, a simulator was used to simulate the behavior of different passenger profiles in an urban area and the results were compared between the lines obtained by the optimization process and existing bus lines in the city of São Paulo. According to our results, optimized bus routes have mean travel time 22% less than the existing route and the time spent between origin/destination has decreased up to 18%.
## Get it running

To get it running you should first set up a server with the open source [OSRM routing engine]([https://linktodocumentation](https://project-osrm.org/)).

After that you should change the hardcoded value of the OWNSERVER variable in the follwing .java file: 

```url
  src/main/java/services/osrm/OsrmAPIRequester.java
```

The new value should be the URL exposed by your OSRM HTTP server.
