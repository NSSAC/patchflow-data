# Methodology

## PatchFlow 1.0

PatchFlow 1.0 is are synthetic mobility networks calculated using radiation models
based on estimated population data from GPW and GADM level 1 and level 2 administrative
regions. 
The networks are calculated using constant outflow fraction (0.01, 0.02, 0.05, 0.10, 0.20  or 0.50).

### Mapping GPW population data to GADM regions

The GADM region geometries (GADM v3.6) were used to aggregate (sum) 
the raster GPW population (GPW v4 at 30“ resolution, using the UN 2020 estimate from GPW). 
The resulting per region population estimate was assigned to the centroids 
of the respective regions (using level 1 and level 2 administrative regions, if available).

The aggregation was done using PostGIS 2.5 (Postgres 11.7).

### Calculating mobility networks
The networks were calculated using [scikit-mobility](​https://github.com/scikit-mobility/scikit-mobility​)
using outflow fraction that is constant for particular network and region's centroids calculated as described above.
For PatchSim, the networks were normalized using the total population of the region.

### Limitations
The current networks are uncalibrated and their relation to the actual mobility 
patterns is not established. While Simini, F, et al. (Nature 484.7392 (2012): 96-100) estimate that the outflow fraction 
for the USA admin 2 level is 0.11 the outflow fraction representative to the particular region
is likely to differ between regions and administrative levels. 
