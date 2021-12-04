# Blue-Bike to Linked GBFS

Prototype to map authoritative [Blue-Bike](https://blue-bike.be) availability and station data to a Linked Data prototype vocabulary of GBFS. It uses an [RML](https://rml.io) to [LDES](https://w3id.org/ldes/specification) workflow and exploits GitHub Actions and GitHub pages to re-publish the data as Linked Open Data.


## Accessing the dataset

You will soon be able to find the metadata of the Linked Data Event Stream at https://www.pieter.pm/Blue-Bike-to-Linked-GBFS/

## The Pipeline

It starts from a private API that Blue-Bike provided to us with availabilities, which you configure using a github secret (see below).

It then boots up an RML processor and maps data into the availabilities LDES compliant to the shape in [availabilities.shacl](availabilities.shacl) (TODO). 

Example station member in the availabilities LDES:
```turtle
<https://blue-bike.be/stations/103#2021-12-04T16:20:12> a gbfs:Station ;
    dct:created "2021-12-04T16:20:12" ;
    dct:isVersionOf <https://blue-bike.be/stations/103> ;
    schema:name "Station Geel" ;
    wgs:latitude "51.168778000000"^^xsd:float ;
    wgs:longitude "4.988778000000"^^xsd:float ;
    gbfs:bikes_available 14 ;
    gbfs:docks_in_use 1 .
```
 

## Github Action configuration

This repository contains a Github Action setup to automatically generate 
LDES data using RML of the Blue-Bike API. 
This API is confidential and must be provided as a Github Repository Secret.

1. Go to *Settings* > *Secrets*
2. Create a new secret using the *New Repository Secret* button
3. Use `BLUEBIKE_API_URL` as name and the URL as value.
Note that the URL must be escaped for `sed`!

Example:

```
Name: BLUEBIKE_API_URL
Value: https:\/\/example.com\/api
```

## License

This initial prototype is funded by the European CEF GreenMov project in collaboration with [Digital Flanders](https://data.vlaanderen.be)


Released under the MIT license.
(c) 2021 IDLab - Ghent University - imec

Authors: 
 - Dylan Van Assche
 - Pieter Colpaert

