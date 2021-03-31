# CityFreight: Collected Data

This data has been made available as part of a research project [Freight Logistics in Smart Cities (CityFreight; project number 308790)](https://prosjektbanken.forskningsradet.no/project/FORISS/308790), funded by the Research Council of Norway and led by [Stein W. Wallace](https://www.nhh.no/en/employees/faculty/stein-w.-wallace/), Professor at NHH Norwegian School of Economics. The aim of this project is to provide public authorities with a toolbox for realistically evaluating major decisions that would make freight transportation in a city more energy-efficient and sustainable.


## `links_Bergen.csv` - Transportation Network of Bergen

This dataset includes all links within the Bergen municipality collected from the NVDB database provided by Statens vegvesen (Norwegian Public Roads Administration) and contains data under the Norwegian licence for Open Government Data (NLOD) distributed by Statens vegvesen. Where it applies, links were matched with speed limits, height restrictions, roadblocks and turn restrictions (also acquired from NVDB). Numerous errors in the data were corrected according to the actual state.

Description of variables:

Variable | Description
-------- | -----------
linkID | Unique identifier of the link
geometry | WKT representation of the link using coordinate system EPSG:5973
startNode | Unique identifier of a node where the link originates
endNode | Unique identifier of a node where the link ends
length | Length of the link in metres
road | *True* if the link is primarily used for driving (corresponds with types *enkelBilveg*, *kanalisertVeg*, *rundkjøring* and *rampe* from NVDB), *False* otherwise
streetName | Name of a street the respective link is part of
streetCode | Unique identifier of a street the respective link is part of
MED | *True* if it is allowed to cover the link in the direction from the start node to the end node, *False* otherwise
MOT | *True* if it is allowed to cover the link in the direction from the end node to the start node, *False* otherwise
speedLimitMED | Speed limit in km/h in the direction from the start node to the end node
speedLimitMOT | Speed limit in km/h in the direction from the end node to the start node
heightRestriction | Maximum height of a vehicle allowed to cover the link
noFlowMED | List of links connected to the end node which are not allowed to continue on due to a turn restriction or a roadblock
noFlowMOT | List of links connected to the start node which are not allowed to continue on due to a turn restriction or a roadblock



## `apartments_Bergen.csv`  -  Apartments in Bergen

The majority of the apartment data has been acquired from Kartverket (Norwegian Mapping Authority) by using information from the annual “Matrikkelen Adresse Leilighetsnivå” (version 2020) under the CC BY 4.0 licence. The data includes official and complete addresses of buildings in the Bergen municipality, together with unique apartments within each building (if there are any). The data includes address, postal district, statistical unit and town. The estimated population at a building/apartment has been generated through a master’s thesis conducted by [Fang and Opedal (2020)](https://hdl.handle.net/11250/2683764). For more information on the estimation, kindly refer to the thesis.

Description of variables:

Variable | Description
-------- | -----------
adressekode | The number that uniquely identifies an addressable street, road, path, place and area entered in the cadastre
adressenavn | The name of a street, road, path, place or area entered in the cadastre
nummer and bokstav | The number and letter that uniquely identifies a building within an addressable street, road, path, square or area
bruksenhetsnummerTekst | A unique apartment identification in a building (if there are any)
offisiellAdresseTekstUtenAdressetilleggsnavn | The official address of a building/apartment
Nord and Øst | The coordinates of the corresponding building/apartment
postnummer | The four-digit post code of a building/apartment
poststed | The name of the post office according to the Norwegian Post
grunnkretsnummer | The four-digit code of a basic statistical unit
grunnkretsnavn | The official name of a basic statistical unit defined by the Statistics Norway
tettstednummer | The four-digit code of a town
tettstednavn | The name of a town defined by Statistics Norway
antallpersoner | The estimated population at a building/apartment



## Travel speed data in Bergen

The travel speed data in Bergen have been collected from an operational work conducted by Statens vegvesen (Norwegian Public Roads Administration) using the simulation software AIMSUN. The dataset is divided into five files with the following variables:

### `speed_simulation_Bergen.csv`  -  Description of the simulation rounds

Variable | Description
-------- | -----------
did | A numeric ID given for a unique simulation
didname | The description of the corresponding simulation
from_time | Starting time of the simulation from the midnight (in seconds)
duration | The duration of the simulation (in seconds)
simdetecintervals | The interval time for capturing data

### `speed_vehicles_Bergen.csv`  -  Information on vehicle types used in the simulation

Variable | Description
-------- | -----------
did | A numeric ID given of a unique simulation
pos | The numeric position of a vehicle type 
oname | The description of the vehicle type

### `speed_detectors_Bergen.csv`  -  Information on detectors located in selected roads to gather the data

Variable | Description
-------- | -----------
id | A numeric ID given for each detector
From_lane | The left most lane where the detector is located
To_lane | The right most lane where the detector is located
xcoord | The X coordinate of the located detector
ycoord | The Y coordinate of the located detector

### `speed_output_Bergen.csv`  -  Generated data from the detectors

Variable | Description
-------- | -----------
oid | The object ID for generating the data, which corresponds to the numeric ID given for each detector
did | A numeric ID given of a unique simulation
sid | The position of the sub-object, which corresponds to the position of a vehicle type in the information table for detectors
ent | A numeric value given for each interval
countveh | The number of vehicles passing by through the detector per interval 
countveh_D | The standard deviation on vehicle count
flow | The number of vehicles passing by through the detector per hour
flow_D | The standard deviation on flow
speed | The average speed of vehicles that are passing by through the detector (km/h)
speed_D | The standard deviation on speed
density | The measurement on the crowdedness of the road, which is based on the number of vehicles per kilometer
density_D | The standard deviation on density
occupancy | The occupancy rate of the corresponding road, which is based on the percentage of time that the detector is active
occupancy_D | The standard deviation on occupancy
headway | Average time interval between the detection of two consecutive vehicle arrivals (in seconds)
headway_D | The standard deviation on headway

### `speed_average_Bergen.csv` - Average speed and flow over all simulations for each vehicle type

Variable | Description
-------- | -----------
id | A numeric ID given for each detector
xcoord | The X coordinate of the located detector
ycoord | The Y coordinate of the located detector
oname | The description of the vehicle type
speed | The average speed of vehicles that are passing by through the detector
flow | The number of vehicles passing by through the detector per hour


