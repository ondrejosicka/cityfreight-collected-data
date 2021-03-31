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



## apartments_Bergen.csv  -  Apartments in Bergen

The majority of the apartment data has been acquired from Kartverket (Norwegian Mapping Authority) by using information from the annual “Matrikkelen Adresse Leilighetsnivå” (version 2020) under the CC BY 4.0 licence. The data includes official and complete addresses of buildings in the Bergen municipality, together with unique apartments within each building (if there are any). The data includes address, postal district, statistical unit and town. The estimated population at a building/apartment has been generated through a master’s thesis conducted by Fang and Opedal (2020) .

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



