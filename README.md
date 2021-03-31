# CityFreight: Collected Data

## links_Bergen.csv  -  Transportation Network of Bergen

This dataset includes all links within the Bergen municipality collected from the NVDB database provided by Statens vegvesen (Norwegian Public Roads Administration) and contains data under the Norwegian licence for Open Government Data (NLOD) distributed by Statens vegvesen. Where it applies, links were matched with speed limits, height restrictions, roadblocks and turn restrictions (also acquired from NVDB). Numerous errors in the data were corrected according to the actual state.

Description of variables:

Variable | Description
-------- | -----------
linkID | Unique identifier of the link
geometry | WKT representation of the link using coordinate system EPSG:5973
startNode | Unique identifier of a node where the link originates
endNode | Unique identifier of a node where the link ends
length | Length of the link in metres
road | True if the link is primarily used for driving (corresponds with types enkelBilveg, kanalisertVeg, rundkjøring and rampe from NVDB), False otherwise
streetName | Name of a street the respective link is part of
streetCode | Unique identifier of a street the respective link is part of
MED | True if it is allowed to cover the link in the direction from the start node to the end node, False otherwise
MOT | True if it is allowed to cover the link in the direction from the end node to the start node, False otherwise
speedLimitMED | Speed limit in km/h in the direction from the start node to the end node
speedLimitMOT | Speed limit in km/h in the direction from the end node to the start node
heightRestriction | Maximum height of a vehicle allowed to cover the link
noFlowMED | List of links connected to the end node which are not allowed to continue on due to a turn restriction or a roadblock
noFlowMOT | List of links connected to the start node which are not allowed to continue on due to a turn restriction or a roadblock
