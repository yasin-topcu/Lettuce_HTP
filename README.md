![Overview](https://github.com/user-attachments/assets/bba8f34c-9272-45e5-8299-18f055aae722)
UAV-based single-plant data extraction workflow

This repository provides a reproducible R-based workflow for extracting single-plant phenotypic traits from UAV RGB imagery using orthomosaic data.

Overview of the experiment

Crop: Lettuce

Planting date: 29 January 2025

UAV phenotyping window: 26, 34, 41, 48, 51, and 54 days after planting (DAP)

Harvest date: 15 April 2025

Flight altitude: 30 m above ground level

Sensor: RGB camera

RGB images were collected during the high-throughput phenotyping window and processed into orthomosaics for single-plant analysis.

Workflow steps

Orthomosaic generation
UAV RGB images were processed into georeferenced orthomosaics (example shown for DAP 54).

Single-plant plot definition
Individual lettuce plants were delineated using polygon shapefiles, where each polygon corresponds to a single plant.

Spatial alignment and masking
Shapefiles were aligned to the orthomosaic coordinate reference system (CRS). Orthomosaics were cropped and masked to the experimental area to improve processing efficiency and accuracy.

Soil removal and canopy isolation
Soil background was removed using color-based masking (HUE index), resulting in isolated plant canopies.

Trait extraction
Pixel-based traits, including canopy pixel count and RGB vegetation indices, were extracted at the single-plant level and compiled into tabular datasets.

Downstream analyses
The extracted single-plant data were used for statistical analyses and machine-learning applications, enabling AI-ready phenomic datasets.

Reproducibility

All image processing, masking, and trait extraction steps are implemented in open-source R scripts using packages such as FIELDimageR, terra, and sf.
The complete, reproducible code used in this study is provided in this GitHub repository.
