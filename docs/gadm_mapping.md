# Mapping GPW population data to GADM regions

The GADM region geometries (GADM v3.6) were used to aggregate (sum) 
the raster GPW population (GPW v4 at 30“ resolution, using the UN 2020 estimate from GPW). 
The resulting per region population estimate was assigned to the centroids 
of the respective regions.

The aggregation was done using PostGIS 2.5 (Postgres 11.7).