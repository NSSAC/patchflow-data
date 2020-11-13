# Description of files
## Networks and supporting files
Each represented region has the following files
### Mobility networks:
 ```sh
 ${ISO_3}/${ISO_3}_admin${ADMIN_LEVEL}_${MOBILITY_MODEL}_${OUTFLOW_FRACTION}.csv
 ```
 | variable | description |
 |----------|-------------|
 |`ISO_3`   | ISO 3166-1 alpha-3 codes corresponding to level 0 of GADM v3.6 |
 |`ADMIN_LEVEL` | Administrative level, currently 1 and 2 if available corresponding to levels 1 and 2 of GADM v3.6 |
 |`MOBILITY_MODEL` | Adopted mobility model, currently `radiation_constant` |
 |`OUTFLOW_FRACTION` | Outflow fraction for the mobility model one of `0.01 0.02 0.05 0.10 0.20 0.50` |



The format of the networks is simple CSV file:
``` 
origin,destination,flow,time
POL.1_1,POL.8_1,396603.0,0
```
    
| field | description |
|-------|-------------|
| `origin` | The originating region. The identifier corresponds to GADM v3.6 region identifier
| `destination` | The destination region. 
| `flow` | The number of people traveling from `origin` to `destination` in a single day
| `time` | The day (relative) for which the flow is calculated if the network is time dependent. Currently not used (time=0), the networks are constant

The network includes *self-loops* (`origin == destination`) i.e. people that are staying within given region.    


### Normalized mobility networks for PatchSim
 ```sh
 ${ISO_3}/${ISO_3}_admin${ADMIN_LEVEL}_${MOBILITY_MODEL}_${OUTFLOW_FRACTION}_normalized.patchsim
 ```
 The variables are the same as above
 The format is a simple space delimited file without a header with the following fields:

| field | description |
|-------|-------------|
| 0     |    `origin` The originating region. The identifier corresponds to GADM v3.6 region identifier
| 1     |    `destination`  The destination region. 
| 2     |     `time`  The day (relative) for which the flow is calculated if the network is time dependent. Currently not used (time=0), the networks are constant
| 3     |    `normalized_flow`  The fraction of people traveling from `origin` to `destination` in a single day. Flows originating from single region (inculding *self-loop*) sum to 1. 


### Supporting files
 1. Regions 
    ```sh
    ${ISO_3}/${ISO_3}_admin${ADMIN_LEVEL}.csv
    ```
    CSV file:
    ```
    PatchName,CENTROID_X,CENTROID_Y,UN_2020_E
    POL.1_1,16.411439530886,51.0904512278866,3110932.9133741
    ```
    | field | description |
    |-------|-------------|
    | `PatchName`  | The identifier corresponds to GADM v3.6 region identifier
    | `CENTROID_X` | The longitude of the region's centroid  
    | `CENTROID_Y` | The latitude of the region's centroid
    | `UN_2020_E`  | The population estimate of the region based on the GPW v4.11 data
    

 1. Population files for PatchSim
    ```sh
     ${ISO_3}/${ISO_3}_admin${ADMIN_LEVEL}_population.patchsim
    ```
    Space separated file with region name (field 0) and population estimate (see description above).

 
