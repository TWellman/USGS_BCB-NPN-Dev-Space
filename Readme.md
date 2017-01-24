National Phenology Network Partnership
=======================================
Data Processing and Visualization Ideas
=======================================


Contacts:
-----------
Tristan Wellman (twellman@usgs.gov), Steven Aulenbach (saulenbach@usgs.gov), and Sky Bristol (sbristol@usgs.gov)

Biogeographic Characterization Branch, Core Science Analytics, Synthesis and Libraries.

A collaborative project with (Ecology) NPN partners


Purpose:
-----------
 This repository contains basic information and exploratory capabilities for retrieving, processing, and visualizing data from the National Phenology Network, which will ultimately become a new integration point within the National Biogeographic Map. The content provided herein mainly shows exploratory work, but is projected to be a hub for ensuing NPN activities and further content synthesis to present NPN content within the National Biogeographic Map.


Audiences:
-----------
 Agricultural farmers, food supply managers and distributors, people involved in pest management, and gardeners; anyone who might utilize one of the many NPN published accumulated growing degree threshold models providing information, such as Spring indices (leaf or bloom). Notably, managers and decision makers at the local, State, and Federal levels with fiscal interests or authorized stewardship of related agricultural or environmental resources.


Development Status:
-------------------
Under development, exploratory python scripts have been created to examine data storage formats, basic statistics, error analysis, table processing, and general plotting. These scripts present functional case examples of processing and displaying NPN data. On deck, our ideas are being refined to production level capabilities for use in the National Biogeographic Map.


Source Code:
--------------
  1) File: NPN_figs_timeseries_on_the_fly_vs_preproc.ipnb

    Test operations:
     (a) Reads a netcdf time series file from NPN Geoserver,
     (b) processes netcdf data slices as numpy masked arrays,
     (c) creates a customized time series box plot,
     (d) creates a customized deviation from historical trend (median) bar plots,
     (e) creates a frequency histogram of results,
     (f) creates a key-value dictionary of plot specification for preprocessing (in progress),
     (g) creates altered plot functions and dictionary of stored preprocessed plot specifications, and
     (h) produces on-the-fly generated plots and equivalent plots generated with preprocessed information.

  2) File: NPN_Process_rasters_output_tables_multiplots.ipnb

    Test operations:
     (a) Reads a raster file from NPN Geoserver and local vector file (shapefile),
     (b) extracts intersecting raster cells per (shapefile) feature (e.g. ecoregion),
     (c) calculates ~20 stat measures for raster cells within in each feature,
     (d) creates key-value dictionaries of data and statistics results,
     (e) creates a dataframe of ~20 measures, per feature examined (rows),
     (f) creates histogram plots per feature (e.g. ecoregion),
     (g) creates a composite dataframe of all features (composite min, max, mean, and stdev),
     (h) plots histograms of min, max, mean, and median results for all features examined, and
     (i) plots composite percentile plots of min, max, mean, and median results (regional result).

  3) File: raster_polygon_calc_method_compare_L3-85polys.ipnb

    Test operations:
    (a) Extracts intersecting raster cells per (shapefile) feature (e.g. ecoregion),
    (b) calculates basic stat measures for raster cells within each feature,
    (c) compares results using only interior vs (inner + intersecting) raster cells (relevant to our analyses), and
    (d) creates histograms of differences by feature between methods per statistic evaluation.



Example Data:
--------------
a) Level III ecoregions (simplified) shapefile with feature uuids, a preliminary reference to  
   the Spatial Feature Registry (folder: Shapefile_us_eco_l3_NAD83_Dissolve)
b) NPN NetCDF example dataset (file: si-x-average_leaf_prism.nc)


Copyright and License:
---------------------
This USGS product is considered to be in the U.S. public domain, and is licensed under
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/).

Although this software program has been used by the U.S. Geological Survey (USGS), no warranty, expressed or implied,
is made by the USGS or the U.S. Government as to the accuracy and functioning of the program and related program
material nor shall the fact of distribution constitute any such warranty, and no responsibility is assumed by the
USGS in connection therewith.
